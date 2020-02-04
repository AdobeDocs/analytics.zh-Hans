---
title: trackDownloadLinks
description: 启用或禁用下载链接的自动链接跟踪。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackDownLoadLinks

Adobe提供跟踪下载链接的功能，无需为每个下载链 `tl()` 接手动设置相应的功能。 如果要对下载链接使用自动链接跟踪，请启用此变量。

启用此功能后，AppMeasurement会将任何已点击的链接URL与中的值进行比较 `downloadLinkFileTypes`。 如果存在匹配项，则自动触发下载链接跟踪调用。

## 在Adobe Experience Platform Launch中跟踪下载链接

配置Adobe Analytics扩展时，跟踪下载链 [!UICONTROL 接是链接跟踪] accordion下的复选框。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“链 [!UICONTROL 接跟踪] ”折叠面板，该面板显示“跟踪 [!UICONTROL 下载链接”复选框] 。

单击此复选框可启用自动下载链接跟踪。

## s.trackDownloadLinks in appMeasurement and Launch自定义代码编辑器

布尔 `s.trackDownloadLinks` 值是启用或禁用自动下载链接跟踪的值。 如果您不想跟踪下载链接，或希望手动调用函数以跟 `tl()` 踪下载，请将此变量设置为 `false`。

```js
s.trackDownloadLinks = true;
```
