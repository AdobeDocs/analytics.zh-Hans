---
description: 跟踪功能可确定您的 Adobe Analytics 实施如何对搜索引擎数据进行跟踪。这是向 Adobe Analytics 数据适当增加搜索引擎数据的必要步骤。
seo-description: 跟踪功能可确定您的 Adobe Analytics 实施如何对搜索引擎数据进行跟踪。这是向 Adobe Analytics 数据适当增加搜索引擎数据的必要步骤。
seo-title: 跟踪手动模式和自动模式
title: 跟踪手动模式和自动模式
uuid: c6ce7901-7b65-48b6-b65 f-f29 cc47 b7454
translation-type: tm+mt
source-git-commit: 463e28e9d710cc41e4ab4ace5e3861b8ae8fbdcc

---


# 跟踪：手动模式和自动模式

跟踪功能可确定您的 Adobe Analytics 实施如何对搜索引擎数据进行跟踪。这是向 Adobe Analytics 数据适当增加搜索引擎数据的必要步骤。

支持两种跟踪模式：自动模式和手动模式。

## 自动跟踪模式 {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

在自动模式下，您可以让 Advertising Cloud 引擎自行决定如何处理搜索引擎数据。这种方法比较简单，但可能不会生成最佳的集成数据集。

因此，选择自动模式时需要选中确认复选框，然后才能保存帐户设置。


请注意，要在“自动模式”中配置搜索引擎帐户，您有责任执行以下操作：

* 将“s_kwcid”参数和值添加到要添加帐户的帐户跟踪模板或登陆页面 URL 中。该参数和值将插入到 URL 的末尾。如果您的 Web 服务器要求在 URL 末尾使用特定的键值对，或者需要更新以支持 URL 中的任何新键值对，则可能需要执行其他操作。**您有责任确保添加的 URL 参数能够正确保持到最终登陆页面。**
* 此外，可以将关键字作为“s_kwcid”值的一部分插入到登陆 URL 中。如果它们包含特殊字符或符号，请确认您的 Web 服务器可以支持这些字符。示例：常见的特殊字符是“+”，用于“修改广泛匹配”关键字。

## 手动跟踪模式 {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

在手动模式下，您需要指定 Advertising Analytics 数据集成流程处理搜索引擎数据的方式。

### 将“手动跟踪”添加到 Google 帐户 {#section_41C1EB1AEB034544A5BC291F53C05C67}

以下显示了需要添加到 Google 帐户的字符串。您需要将该字符串添加到您的帐户所使用的所有跟踪模板中。

>[!IMPORTANT]
>
>`<Advertising Analytics ID>` 值( **粗体** 下)为通用值， **必须替换为特定帐户ID字符串**。您可以在帐户设置页面中的“跟踪”部分下，获得特定帐户 ID 字符串。

**适用于促销活动的跟踪字符串：**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![](assets/Google.png)

各种跟踪模板格式中的跟踪代码示例：

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`具有其他URL参数**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**第三方(DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**第三方(DoubleClick)`{lpurl}`**

如果 URL 经过重定向并且没有使用“unescapedlpurl”值，则需要对字符串进行足够次数的编码，以便在重定向到最终登陆页面 URL 的过程中一直保留该字符串。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### 将“手动跟踪”添加到 Bing 帐户 {#section_094F8ACA493C4D65B1F54A695558EBF2}

以下显示了需要添加到 Bing 帐户的字符串。您需要将该字符串添加到您的帐户所使用的所有跟踪模板中。

>[!IMPORTANT]
>
>`<Advertising Analytics ID>` 值( **粗体** 下)为通用值， **必须替换为特定帐户ID字符串**。您可以在帐户设置页面中的“跟踪”部分下，获得特定帐户 ID 字符串。

**适用于促销活动的跟踪字符串：**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

各种跟踪模板格式中的跟踪代码示例：

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}`
```

**`{lpurl}`具有其他URL参数**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**第三方(DoubleClick)'{unescreclick purl}**

```https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}

```

**第三方(DoubleClick)`{lpurl}`**

如果 URL 经过重定向并且没有使用“unescapedlpurl”值，则需要对字符串进行足够次数的编码，以便在重定向到最终登陆页面 URL 的过程中一直保留该字符串。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
