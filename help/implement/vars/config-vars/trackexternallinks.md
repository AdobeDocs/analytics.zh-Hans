---
title: trackExternalLinks
description: 对退出链接启用或禁用自动链接跟踪。
translation-type: tm+mt
source-git-commit: 94218548dc4e3efd57df95c992003e94640e4330

---


# trackExternalLinks

Adobe offers the ability to track outbound links without manually setting the [`tl()`](../functions/tl-method.md) method for each exit link. 如果要对退出链接使用自动链接跟踪，则启用此变量。

启用此功能后，AppMeasurement 会将任何点击的链接 URL 与 [`linkInternalFilters`](linkinternalfilters.md) 和 [`linkExternalFilters`](linkexternalfilters.md) 中的值进行比较。如果存在匹配项，则会自动触发退出链接跟踪调用。

## Adobe Experience Platform Launch 中的“跟踪出站链接”

“跟踪出站链接”是配置 Adobe Analytics 扩展时位于[!UICONTROL 链接跟踪]折叠面板下的复选框。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的]配置[!UICONTROL 按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 跟踪出站链接]复选框。

单击此复选框可启用自动退出链接跟踪。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.trackExternalLinks

`s.trackExternalLinks` 是一个布尔值，用于启用或禁用自动退出链接跟踪。If you do not want to track outbound links, or would prefer to manually call the `tl()` method to track exit links, set this variable to `false`.

```js
s.trackExternalLinks = true;
```
