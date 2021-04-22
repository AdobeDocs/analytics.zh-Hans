---
title: trackInlineStats
description: 在您的实施中启用或禁用 Activity Map。
keywords: 禁用 Activity Map
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '192'
ht-degree: 100%

---

# trackInlineStats

Activity Map 是 Adobe Analytics 中的一项功能，可收集访客点击位置及其点击内容的相关数据。您可以在 Analytics 报表中或使用浏览器扩展叠加查看此数据。如果要使用 Activity Map 功能，则启用此变量。

启用此功能后，AppMeasurement 会收集有关链接的信息，并在下一个图像请求中发送该数据。每次点击的信息都存储在标记为 `s_sq` 的 Cookie 中。

## Adobe Experience Platform Launch 中的“启用 Clickmap”

[!UICONTROL 启用 Clickmap] 是配置 Adobe Analytics 扩展时位于[!UICONTROL 链接跟踪]折叠面板下的复选框。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的]配置[!UICONTROL 按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 启用 Clickmap] 复选框。

单击此复选框可启用 Activity Map 跟踪。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.trackInlineStats

`s.trackInlineStats` 是一个布尔值，用于启用或禁用自动 Activity Map 跟踪。其默认值为 `false`。如果要启用 Activity Map 数据收集，则将此值设置为 `true`。

```js
s.trackInlineStats = true;
```
