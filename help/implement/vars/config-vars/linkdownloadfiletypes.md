---
title: linkDownloadFileTypes
description: 确定自动作为下载链接进行跟踪的文件扩展名。
feature: Appmeasurement Implementation
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
TQID: https://experienceleague.adobe.com/xe-ClVo-348u2ash9QODi2hIdGrVv6sIeN739EfPZ7c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 419
ht-degree: 57%

---

# linkDownloadFileTypes

当启用了[`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement)或[`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK)并且访客单击某个链接时，AppMeasurement会检查该链接的URL以获取文件类型扩展。 如果链接URL包含匹配的文件类型，则会自动发送下载链接图像请求。

使用 `linkDownloadFileTypes` 可自定义要计为下载链接的文件扩展名。

>[!NOTE]
>
>只自动跟踪实际点击量。 不会自动跟踪以下类型的链接：
>
>* 加载页面时自动启动的文件下载
>* 重定向后触发的下载
>* 右键单击并选择“将目标另存为...”
>* 使用 JavaScript 的链接，例如 `javascript:openLink()`
>
>对于这些下载类型，您可以手动发送[`link tracking`](../functions/tl-method.md)调用。

如果点击的链接与退出链接和下载链接标准均匹配，则将优先使用下载链接类型。

## 使用Web SDK扩展下载链接限定符

[!UICONTROL 下载链接限定符]文本字段使用正则表达式来确定点击的链接是否符合下载链接的资格。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL Adobe Experience Platform Web SDK]下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 在[!UICONTROL 数据收集]下，在&#x200B;**[!UICONTROL 下载链接限定符]**&#x200B;文本字段中设置所需的值。

## 手动实施Web SDK的下载链接限定符

[&#128279;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans)使用[`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=zh-Hans#automaticLinkTracking)配置 SDK。 该字段对单击的URL使用正则表达式来确定它是否为有效的下载链接。 如果未定义`downloadLinkQualifier`，则默认值设置为`\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`。

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## 使用Adobe Analytics扩展下载扩展

“下载扩展”是文件扩展名的列表，其中包含一个字段，用于在配置 Adobe Analytics 扩展时在[!UICONTROL 链接跟踪]折叠面板下添加更多内容。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**配置**&#x200B;按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示&#x200B;**[!UICONTROL 下载扩展]**&#x200B;字段。

通过在字段中输入文本并单击&#x200B;**[!UICONTROL 添加]**，可将文件扩展名添加到列表中。 通过单击相应的&#x200B;**&#39;X&#39;**&#x200B;图标，可从列表中删除文件扩展名。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 变量是以逗号分隔的文件扩展名字符串。 请勿使用空格。

如果未定义此变量，则自动下载链接跟踪将不起作用（即使 [`trackDownloadLinks`](trackdownloadlinks.md) 为 `true`）。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
