---
title: 智能数据平滑
description: 了解智能数据平滑功能如何分析历史趋势以预测受影响时间段内任何量度的值。
feature: AI 工具
role: User, Admin
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 5%

---

# 智能数据平滑

在极少数情况下，某些因素可能会影响数据质量。 机器人流量、实施更改或服务中断都可能影响所收集数据的完整性。 它们还会使有关事件可能如何影响数据完整性的分析变得复杂。

智能数据平滑功能是[Analytics Labs](/help/analyze/tech-previews/overview.md)中的一个原型，可通过分析历史趋势来预测受影响时间段内任何量度的值，从而帮助完成此视图。 该原型应用高级机器学习算法来绘制正在分析的时间段内量度的预期值。

## 运行智能数据平滑功能

1. 导航到Adobe Analytics Labs:
   ![Labs](assets/labs.png)
1. 启动智能数据平滑原型。
   ![Launch原型](assets/intelligent-ds.png)
1. 将必须分析的量度添加到自由格式表。 原型仅适用于每日粒度，因此请确保表中的维度为“日”。
   ![添加量度](assets/add-metric.png)
1. 选择比事件窗口更宽的日期范围，但确保它包含事件。
   ![日期范围](assets/date-range.png)
1. 单击自由格式表中量度的齿轮图标。
   ![齿轮图标](assets/gear-icon.png)
1. 在[!UICONTROL 数据设置]下，选择[!UICONTROL 数据平滑]选项。
   ![数据平滑](assets/column-setting.png)
1. 选择与事件对应的日期/日期范围，然后单击[!UICONTROL Apply]。
确保数据平滑的数据范围是为面板选择的日期范围的子集。 表格和图表中的量度将被预测值替换。
   ![预测值](assets/predictive-values.png)