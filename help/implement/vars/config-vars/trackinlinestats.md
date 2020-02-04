---
title: trackInlineStats
description: 在您的实施中启用或禁用活动图。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

活动地图是Adobe Analytics中的一项功能，可收集访客点击位置及其点击内容的相关数据。 您可以在Analytics报告中或使用浏览器扩展叠加查看此数据。 如果要使用活动映射功能，请启用此变量。

启用此功能后，AppMeasurement会收集有关链接的信息，并在下一个图像请求中发送该数据。 每次单击的信息都存储在标有cookie的Cookie中 `s_sq`。

## 在Adobe Experience Platform Launch中启用Clickmap

[!UICONTROL 配置Adobe Analytics扩展时] ,“链接跟踪” [!UICONTROL 折叠面板下方的复选框“启用Clickmap] ”。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“链 [!UICONTROL 接跟踪] ”折叠面板，该面板显示“启用 [!UICONTROL Clickmap] ”复选框。

单击此复选框可启用活动图跟踪。

## AppMeasurement中的s.trackInlineStats和启动自定义代码编辑器

该布 `s.trackInlineStats` 尔值可启用或禁用活动映射跟踪。 Its default value is `false`. 如果要启用活 `true` 动图数据收集，请将此值设置为。

```js
s.trackInlineStats = true;
```
