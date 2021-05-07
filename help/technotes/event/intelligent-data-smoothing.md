---
title: 智能数据平滑
description: 了解智能数据平滑功能如何分析历史趋势以预测受影响时间段内任何指标的价值。
feature: AI 工具
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: aa9f0a8f5b7b1780d0b0be729775c573e12caa35
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 2%

---

# 智能数据平滑

在某些情况下，某些因素会影响数据质量。 流量、实施更改或服务中断都可能影响所收集数据的完整性。 这也使事件如何影响数据完整性的分析变得复杂。

智能数据平滑是[Analytics Labs](/help/analyze/tech-previews/overview.md)中的一个原型，它可以通过分析历史趋势来预测受影响时间段内任何指标的值，从而帮助完成此视图。 该原型应用高级机器学习算法绘制被分析时间段内的量度的预期值。

## 运行智能数据平滑

1. 导航到Adobe Analytics实验室：
   ![Labs](assets/labs.png)
1. 启动智能数据平滑原型。
   ![启动原型](assets/intelligent-ds.png)
1. 将必须分析的量度添加到自由格式表。 原型仅适用于每日粒度，因此请确保表中的维度为“天”。
   ![添加量度](assets/add-metric.png)
1. 选择比事件窗口宽的日期范围，但确保其包含事件。
   ![日期范围](assets/date-range.png)
1. 在“自由形式”(Freeform)表格中单击量度的齿轮图标。
   ![齿轮图标](assets/gear-icon.png)
1. 在[!UICONTROL 数据设置]下，选择[!UICONTROL 数据平滑]选项。
   ![数据平滑](assets/column-setting.png)
1. 选择与事件对应的日期/日期范围，然后单击[!UICONTROL 应用]。
确保数据平滑的数据范围是为面板选择的日期范围的子集。 表格和图表中的量度被预测值替换。
   ![预测值](assets/predictive-values.png)