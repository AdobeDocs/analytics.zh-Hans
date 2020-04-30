---
description: 显示如何生成简单的“每次访问页面查看次数”量度。
title: 构建简单的“每次访问的页面查看次数”量度
uuid: 0730e51c-1f8f-473b-8825-d72911f2944c
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 构建简单的“每次访问的页面查看次数”量度

显示如何生成简单的“每次访问页面查看次数”量度。

有关 UI 组件的详细描述，请参阅[生成量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)。

下面说明了如何生成简单的“每次访问页面查看次数”量度。

1. 导航至计算量度生成器。
1. 为量度指定“每次访问页面查看次数”或类似的名称。
1. Give it a user-friendly **[!UICONTROL Description]** to show what it&#39;s used for.
1. Select the right **[!UICONTROL Format]**, in this case Decimal.
1. 确定您希望报表显示多少个小数位。
1. 设置量度极性。对于此量度，上升趋势是有利的（绿色）。
1. Add a **[!UICONTROL Tag]** to organize your metrics.
1. 对于此量度，首先将“页面查看次数”拖到画布中，然后再将“访问次数”拖到下方（等到出现蓝线时再放下它）。
1. 选择“除以”运算符。（“除以”是默认的运算符。）
1. You can now see a **[!UICONTROL Preview]** of that metric as you are building it, at the top right.
1. 产品兼容性显示该量度是与“[当前数据](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html)”兼容，还是仅与“完全处理数据”兼容。
1. 单击 **[!UICONTROL Save]**.
1. Notice that the **[!UICONTROL Summary]** formula updates anytime you make a change to the metric definition.
1. 此时您会自动转到[计算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)，它类似于区段管理器。它允许您共享、批准、（重新）标记、重命名或删除量度。

