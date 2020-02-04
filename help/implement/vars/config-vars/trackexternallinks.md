---
title: trackExternalLinks
description: 启用或禁用退出链接的自动链接跟踪。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackExternalLinks

Adobe提供跟踪出站链接的功能，无需为每个退出链 `tl()` 接手动设置函数。 如果要对退出链接使用自动链接跟踪，请启用此变量。

启用此功能后，AppMeasurement会将任何已点击的链接URL与和中的值 `linkInternalFilters` 进行比较 `linkExternalFilters`。 如果存在匹配项，则会自动触发退出链接跟踪调用。

## 在Adobe Experience Platform Launch中跟踪出站链接

配置Adobe Analytics扩展时，跟踪出站链 [!UICONTROL 接是“链接跟踪] ”折叠面板下的复选框。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“链 [!UICONTROL 接跟踪] ”折叠面板，该面板显示“跟踪 [!UICONTROL 出站链接”复选框] 。

单击此复选框可启用自动退出链接跟踪。

## AppMeasurement中的s.trackExternalLinks和启动自定义代码编辑器

该布 `s.trackExternalLinks` 尔值可启用或禁用自动退出链接跟踪。 如果您不想跟踪出站链接，或希望手动调用函数以跟踪退出链 `tl()` 接，请将此变量设置为 `false`。

```js
s.trackDownloadLinks = true;
```
