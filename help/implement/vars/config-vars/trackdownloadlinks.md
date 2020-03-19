---
title: trackDownloadLinks
description: 启用或禁用下载链接的自动链接跟踪。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

Adobe提供跟踪下载链接的功能，无需为每个下载链 [`tl()`](../functions/tl-method.md) 接手动设置方法。 如果要对下载链接使用自动链接跟踪，请启用此变量。

启用此功能后，AppMeasurement会将任何已点击的链接URL与中的值进行比较 [`linkDownloadFileTypes`](linkdownloadfiletypes.md)。 如果存在匹配项，则自动触发下载链接跟踪调用。

## 在Adobe Experience Platform Launch中跟踪下载链接

配置Adobe Analytics扩展时，“跟踪下载链接” [!UICONTROL Link Tracking] 是accordion下的复选框。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Extensions] 然后单击“Adobe Analytics” [!UICONTROL Configure] 下的按钮。
4. 展开折叠 [!UICONTROL Link Tracking] 面板，该面板会显示该 [!UICONTROL Track download links] 复选框。

单击此复选框可启用自动下载链接跟踪。

## s.trackDownloadLinks in AppMeasurement and Launch自定义代码编辑器

布尔 `s.trackDownloadLinks` 值是启用或禁用自动下载链接跟踪的值。 如果您不想跟踪下载链接，或希望手动调用方法来跟 `tl()` 踪下载，请将此变量设置为 `false`。

```js
s.trackDownloadLinks = true;
```
