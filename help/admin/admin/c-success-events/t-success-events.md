---
description: 描述如何配置成功事件的步骤。
title: 配置成功事件
topic: Admin tools
uuid: ca3d3f46-5fad-4481-aef6-04cad6bc6e2d
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# 配置成功事件

描述如何配置成功事件的步骤。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 选择报表包。
1. 单击 **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![步骤结果](assets/success_event_page.png)

1. In the **[!UICONTROL Name]** column, select the checkbox next each item to enable editing, then specify the desired name.
1. In the **[!UICONTROL Type]** column, select the checkbox next each item to enable the drop-down list, then select the desired type.

   >[!NOTE]
   >
   >在更改事件类型之前，请参阅[更改事件类型](/help/admin/admin/c-success-events/event-type.md)。

   有关这些元素的信息，请参阅[成功事件页面 - 描述](/help/admin/admin/c-success-events/success-event.md)。

1. In the **[!UICONTROL Polarity]** column, specify whether an upward trend for this metric is good or bad.
1. In the **[!UICONTROL Visibility]** column, you can hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder.

   这项设置不影响相关量度或事件的数据收集，而只会影响该量度或事件在用户界面中的可见性。[更多...](/help/admin/admin/metric-visibility.md)
1. 提供描述。
1. 选择是否始终记录该事件。
1. 启用或禁用[参与率量度](/help/components/c-variables/c-metrics/metrics-participation.md)。

   >[!NOTE]
   >
   >您最多可以为 100 个自定义事件启用参与率。除此之外，您还可以在[计算量度](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/participation-metric.html)生成器中创建参与率量度。

1. 单击 **[!UICONTROL Save]**.

