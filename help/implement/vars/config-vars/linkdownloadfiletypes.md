---
title: linkDownloadFileTypes
description: 确定自动作为下载链接进行跟踪的文件扩展名。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkDownloadFileTypes

When [`trackDownloadLinks`](trackdownloadlinks.md) is enabled and a visitor clicks on a link, AppMeasurement checks the URL of the link for filetype extensions. 如果链接 URL 包含的文件类型可在 `linkDownloadFileTypes` 中找到，则会自动发送下载链接图像请求。

使用 `linkDownloadFileTypes` 可自定义要计为下载链接的文件扩展名。

>[!NOTE] 只自动跟踪实际点击量。不会自动跟踪以下类型的链接：
>
> * 加载页面时自动启动的文件下载
> * 重定向后触发的下载
> * 右键单击并选择“将目标另存为...”
> * 使用 JavaScript 的链接，例如 `javascript:openLink()`
>
> 
For these download types, you can manually call the [`tl()`](../functions/tl-method.md) method.

如果点击的链接与退出链接和下载链接标准均匹配，则将优先使用下载链接类型。

## Adobe Experience Platform Launch 中的“下载扩展”

Download Extensions is a list of file extensions with a field to add more under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展开可 [!UICONTROL Link Tracking] 折叠面板，以显示 [!UICONTROL Download Extensions] 字段。

Add file extensions to the list by entering text in the field and clicking [!UICONTROL Add]. 单击相应的“X”图标，从列表中删除文件扩展名。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 变量是以逗号分隔的文件扩展名字符串。请勿使用空格。

如果未定义此变量，则自动下载链接跟踪将不起作用（即使 [`trackDownloadLinks`](trackdownloadlinks.md) 为 `true`）。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
