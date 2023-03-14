---
title: linkDownloadFileTypes
description: 确定自动作为下载链接进行跟踪的文件扩展名。
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 56%

---

# linkDownloadFileTypes

时间 [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement)或 [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK)已启用并且访客单击某个链接时，AppMeasurement会检查该链接的URL以获取文件类型扩展。 如果链接URL包含匹配的文件类型，则会自动发送下载链接图像请求。

使用 `linkDownloadFileTypes` 可自定义要计为下载链接的文件扩展名。

>[!NOTE]
>
>只自动跟踪实际点击量。不会自动跟踪以下类型的链接：
>
>* 加载页面时自动启动的文件下载
>* 重定向后触发的下载
>* 右键单击并选择“将目标另存为...”
>* 使用 JavaScript 的链接，例如 `javascript:openLink()`
>
>对于这些下载类型，您可以手动发送 [`link tracking`](../functions/tl-method.md) 呼叫。

如果点击的链接与退出链接和下载链接标准均匹配，则将优先使用下载链接类型。

## 使用Web SDK扩展下载链接限定符

此 [!UICONTROL 下载链接限定符] 文本字段使用正则表达式来确定点击的链接是否符合下载链接的资格。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection?lang=zh-Hans)。
1. 单击所需的标记属性。
1. 转到 [!UICONTROL 扩展] 选项卡，然后单击 **[!UICONTROL 配置]** 按钮位于 [!UICONTROL Adobe Experience Platform Web SDK].
1. 下 [!UICONTROL 数据收集]，在中设置所需的值 **[!UICONTROL 下载链接限定符]** 文本字段。

## 手动实施Web SDK的下载链接限定符

[配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans) SDK使用 [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking). 字段对单击的URL使用正则表达式来确定它是否为有效的下载链接。 如果 `downloadLinkQualifier` 未定义，默认值设置为 `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## 使用Adobe Analytics扩展下载扩展

“下载扩展”是文件扩展名的列表，其中包含一个字段，用于在配置 Adobe Analytics 扩展时在[!UICONTROL 链接跟踪]折叠面板下添加更多内容。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;]**配置**[!UICONTROL &#x200B;按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示&#x200B;**[!UICONTROL 下载扩展]**&#x200B;字段。

通过在字段中输入文本并单击&#x200B;**[!UICONTROL 添加]**，可将文件扩展名添加到列表中。通过单击文件扩展名对应的文件扩展名可从列表中删除 **&#39;X&#39;** 图标。

## AppMeasurement和Analytics扩展代码编辑器中的s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 变量是以逗号分隔的文件扩展名字符串。请勿使用空格。

如果未定义此变量，则自动下载链接跟踪将不起作用（即使 [`trackDownloadLinks`](trackdownloadlinks.md) 为 `true`）。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
