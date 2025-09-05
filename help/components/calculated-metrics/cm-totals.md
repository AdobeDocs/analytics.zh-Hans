---
title: 计算量度总计
description: 了解Analysis Workspace中的计算量度总计
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 94%

---

# 计算量度总计

在 Analysis Workspace 中查看数据时，大多数情况下都会显示计算量度总计。在某些情况下则无法提供“总计”，例如，当报表行采用混合格式（例如，小数和货币）时。

显示“总计”时，量度通常在服务器端进行计算，这意味着“总计”删除了重复量度（例如，访问或访客）。在某些情况下，计算量度是在客户端通过表行相加生成，这意味着“总计”不会删除重复量度（例如，访问或访客）。这种情况出现于：

* 当自由格式表中使用了[静态行](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)，并且选择了&#x200B;**[!UICONTROL 显示为当前行的总和]**￼选项（默认）时。
* 在[圆环可视化图表](/help/analyze/analysis-workspace/visualizations/donut.md)中，这是为了使数字相加总和等于 100%。

有关 Analysis Workspace 中总计的更多信息，请访问 [Workspace 总计](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total)。
