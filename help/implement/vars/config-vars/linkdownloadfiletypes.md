---
title: linkDownloadFileTypes
description: 确定自动作为下载链接跟踪的文件扩展名。
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkDownloadFileTypes

当设 `trackDownloadLinks` 置为并且 `true` 访客单击某个链接时，AppMeasurement会检查该链接的URL以获取文件类型扩展。 如果链接URL包含中找到的文件类型， `linkDownloadFileTypes`则会自动发送下载链接图像请求。

使用 `linkDownloadFileTypes` 自定义要计为下载链接的文件扩展名。

> [!NOTE] 只自动跟踪实际的单击。 不会自动跟踪以下类型的链接：
>
> * 载入页面时自动开始的文件下载
> * 重定向后触发的下载
> * 右键单击并选择“将目标另存为……”
> * 使用JavaScript的链接，例如 `javascript:openLink()`
>
> 
对于这些下载类型，您可以手动调用该函 `tl()` 数。

如果单击的链接与退出链接和下载链接条件均匹配，则下载链接类型将优先。

## 下载Adobe Experience Platform Launch中的扩展

“下载扩展”是一个文件扩展的列表，其中包含一个字段，用于在配置Adobe Analytics扩展时在“链 [!UICONTROL 接跟踪] ”折叠面板下添加更多内容。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“链 [!UICONTROL 接跟踪] ”折叠面板，该面板显示“ [!UICONTROL 下载扩展] ”字段。

在字段中输入文本并单击“添加”，将文件扩展名添加到列 [!UICONTROL 表中]。 单击相应的X图标，从列表中删除文件扩展名。

## s.linkDownloadAppMeasurement和启动自定义代码编辑器中的FileTypes

变量 `s.linkDownloadFileTypes` 是以逗号分隔的文件扩展名的字符串。 请勿使用空格。

如果未定义此变量，则自动下载链接跟踪将不起作用(即使 `trackDownloadLinks` 是 `true`)。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v"
```
