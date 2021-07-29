---
title: trackExternalLinks
description: 对退出链接启用或禁用自动链接跟踪。
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 87%

---

# trackExternalLinks

Adobe 提供跟踪出站链接的功能，无需为每个退出链接手动设置 [`tl()`](../functions/tl-method.md) 方法。如果要对退出链接使用自动链接跟踪，则启用此变量。

启用此功能后，AppMeasurement 会将任何点击的链接 URL 与 [`linkInternalFilters`](linkinternalfilters.md) 和 [`linkExternalFilters`](linkexternalfilters.md) 中的值进行比较。如果存在匹配项，则会自动触发退出链接跟踪调用。

## 使用Adobe Experience Platform中的标记跟踪出站链接

“跟踪出站链接”是配置 Adobe Analytics 扩展时位于[!UICONTROL 链接跟踪]折叠面板下的复选框。

1. 使用您的Adobe ID凭据登录到[数据收集UI](https://experience.adobe.com/data-collection)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的]配置[!UICONTROL 按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 跟踪出站链接]复选框。

单击此复选框可启用自动退出链接跟踪。

## AppMeasurement 和 自定义代码编辑器中的 s.trackExternalLinks

`s.trackExternalLinks` 是一个布尔值，用于启用或禁用自动退出链接跟踪。如果您不想跟踪出站链接，或希望手动调用 `tl()` 方法以跟踪退出链接，则将此变量设置为 `false`。

```js
s.trackExternalLinks = true;
```
