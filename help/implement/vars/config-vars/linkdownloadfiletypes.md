---
title: linkDownloadFileTypes
description: 确定自动作为下载链接进行跟踪的文件扩展名。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 100%

---


# linkDownloadFileTypes

当启用了 [`trackDownloadLinks`](trackdownloadlinks.md) 并且访客单击某个链接时，AppMeasurement 会检查该链接的 URL 以获取文件类型扩展。如果链接 URL 包含的文件类型可在 `linkDownloadFileTypes` 中找到，则会自动发送下载链接图像请求。

使用 `linkDownloadFileTypes` 可自定义要计为下载链接的文件扩展名。

>[!NOTE]
>
> 只自动跟踪实际点击量。不会自动跟踪以下类型的链接：
>
> * 加载页面时自动启动的文件下载
> * 重定向后触发的下载
> * 右键单击并选择“将目标另存为...”
> * 使用 JavaScript 的链接，例如 `javascript:openLink()`
>
> 对于这些下载类型，您可以手动调用 [`tl()`](../functions/tl-method.md) 方法。

如果点击的链接与退出链接和下载链接标准均匹配，则将优先使用下载链接类型。

## Adobe Experience Platform Launch 中的“下载扩展”

“下载扩展”是文件扩展名的列表，其中包含一个字段，用于在配置 Adobe Analytics 扩展时在[!UICONTROL 链接跟踪]折叠面板下添加更多内容。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的]配置[!UICONTROL 按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 下载扩展]字段。

通过在字段中输入文本并单击[!UICONTROL 添加]，可将文件扩展名添加到列表中。通过单击相应的“X”图标，可从列表中删除文件扩展名。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 变量是以逗号分隔的文件扩展名字符串。请勿使用空格。

如果未定义此变量，则自动下载链接跟踪将不起作用（即使 [`trackDownloadLinks`](trackdownloadlinks.md) 为 `true`）。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
