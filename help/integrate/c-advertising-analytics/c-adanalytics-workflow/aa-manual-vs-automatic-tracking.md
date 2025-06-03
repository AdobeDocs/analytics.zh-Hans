---
description: 跟踪类型确定Adobe Analytics实施如何跟踪您的搜索引擎数据。 此跟踪类型是用搜索引擎数据正确增加Adobe Analytics数据的必要步骤。
title: 跟踪类型
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 29%

---

# 跟踪类型

跟踪类型确定Adobe Analytics实施如何跟踪您的搜索引擎数据。 此跟踪类型是用搜索引擎数据正确增加Adobe Analytics数据的必要步骤。

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

-->

支持两种跟踪模式：[!UICONTROL 自动]和[!UICONTROL 手动]。

## [!UICONTROL 自动]跟踪 {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

[!UICONTROL 自动]跟踪允许Advertising Cloud引擎决定如何处理搜索引擎数据。 自动跟踪是一种更简单的方法，但可能不会生成最佳的集成数据集。

因此，选择&#x200B;**[!UICONTROL 自动]**&#x200B;时需要选中确认复选框，然后才能保存帐户设置。

请注意，若要使用&#x200B;**[!UICONTROL Auto]**&#x200B;类型配置搜索引擎帐户，您需要执行以下操作：

* `s_kwcid`参数和值已添加到要添加帐户的帐户跟踪模板或登陆页面URL中。 此参数和值插入到URL的末尾。 如果您的Web服务器要求在URL末尾使用特定的`key=value`对，则可能需要执行其他操作。 或者更新以支持URL中的任何新`key=value`对。 您有责任确保添加的URL参数能够正确保持到最终登陆页面。
* 此外，还可以将关键字作为 `s_kwcid` 值的一部分插入到登陆 URL 中。如果它们包含特殊字符或符号，请确认您的 Web 服务器可以支持这些字符。例如，一个常见的特殊字符是`+`，该字符用于“修改广泛匹配”关键字。

>[!IMPORTANT]
>
>了解关于是否应将该 `s_kwcid` 参数添加到您的[内容安全策略](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/reference/csp)的更多信息。

## 手动跟踪 {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

通过手动跟踪，您可以指定Advertising Analytics数据集成流程处理搜索引擎数据的方式。

### 将手动跟踪添加到Google帐户 {#section_41C1EB1AEB034544A5BC291F53C05C67}

以下显示了需要添加到 Google 帐户的字符串。您需要将该字符串添加到您的帐户所使用的所有跟踪模板中。

>[!IMPORTANT]
>
>*`<Advertising Analytics ID>`* 值（下面显示为&#x200B;**粗体**&#x200B;的内容）是一个泛指的值，**必须将其替换为您的特定帐户 ID 字符串**。您可以从帐户屏幕的[!UICONTROL 跟踪]部分下获取特定的帐户ID字符串。

**适用于促销活动的跟踪字符串：**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![Google](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/google-account.png)

各种跟踪模板格式中的跟踪代码示例：

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`与其他 URL 参数**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**第三方 (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**第三方 (DoubleClick)`{lpurl}`**

要确保字符串在重定向到最终登陆页面URL的过程中持续存在，您需要对字符串进行充分编码：

* 如果URL经过重定向，并且
* 未使用“unescapedlpurl”值。


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### 将手动跟踪添加到Microsoft Advertising帐户 {#section_094F8ACA493C4D65B1F54A695558EBF2}

以下显示了需要添加到Microsoft Advertising帐户的字符串。 您需要将该字符串添加到您的帐户所使用的所有最终 URL 后缀中。

>[!IMPORTANT]
>
>_`<Advertising Analytics ID>`_值（下面显示为&#x200B;**粗体**&#x200B;的内容）是一个泛指的值，**必须将其替换为您的特定帐户 ID 字符串**。您可以从帐户屏幕的“跟踪”部分下获取特定的帐户ID字符串。

**适用于促销活动的跟踪字符串：**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![添加跟踪代码参数](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

各种最终 URL 后缀格式中的跟踪代码示例：

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`与其他 URL 参数**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**第三方 (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**第三方 (DoubleClick)`{lpurl}`**

要确保字符串在重定向到最终登陆页面URL的过程中持续存在，您需要对字符串进行充分编码：

* 如果URL经过重定向，并且
* 未使用“unescapedlpurl”值。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
