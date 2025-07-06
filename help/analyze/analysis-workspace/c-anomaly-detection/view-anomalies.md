---
description: 了解如何在Analysis Workspace中查看和分析数据异常。
title: 查看异常
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 49%

---

# 查看异常

您可以在Analysis Workspace中的表或折线图中查看异常。

## 在表中查看异常 {#section_869A87B92B574A38B017A980ED8A29C5}

您可以在时间序列自由格式表中查看异常。

1. 在列标题中选择![Setting](/help/assets/icons/Setting.svg)，然后确保在选项列表中选择&#x200B;**[!UICONTROL Anomalies]**&#x200B;选项。 有关更多信息，请参阅[列设置](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)。

1. 异常情况如下表所示：

   检测到![异常](assets/anomaly-detected.png)

   ◥显示在检测到数据异常的每一行的右上角。

   每行&#x200B;**中的**&#x200B;彩色垂直线➋表示预期值。 每行&#x200B;**中的**&#x200B;彩色阴影区域➊表示实际值。 线条（预期值）与阴影区域（实际值）的比较方式决定是否存在异常。（根据[异常检测中使用的统计技术](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)中描述的高级统计技术，将观测视为异常。）

1. 选择行右上角的◥查看有关异常的详细信息。 这显示了实际值偏离预期值以上或以下的程度（以百分比表示）。
1. 选择[打开贡献分析](run-contribution-analysis.md)以开始贡献分析。

## 在折线图中查看异常

折线图是唯一允许您查看异常情况的可视化图表。

要在折线图中查看异常，请执行以下操作：

1. 在可视化图表标题中选择![设置](/help/assets/icons/Setting.svg)，然后确保在选项列表中选择&#x200B;[!UICONTROL **显示异常**]&#x200B;选项。 有关更多信息，请参阅[折线图](/help/analyze/analysis-workspace/visualizations/line.md)。

1. （可选）要允许置信度间隔缩放图表，请在可视化图表标题中选择![设置](/help/assets/icons/Setting.svg)，然后选择选项&#x200B;**[!UICONTROL 允许异常缩放Y轴]**。

   默认情况下不选择此选项，因为它有时会使图表不那么清晰。

   异常情况如下折线图所示：

   ![异常检测到的折线图可视化图表](assets/anomaly-detected-line.gif)

   当检测到数据异常时，**白点**&#x200B;出现在折线上。（根据[异常检测中使用的统计技术](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)中描述的高级统计技术，将观测视为异常。）

   **浅色阴影区域**&#x200B;是值应该出现的置信带或预期范围。超出此预期范围的任何值都是异常。

   如果折线图中包含多个量度，仅显示异常，您必须将鼠标悬停在每个异常上，才能查看该量度的置信带。

   **虚线**&#x200B;是确切的预期值。

1. 选择异常（白点）以查看以下信息：

   * 异常发生的日期。

   * 异常的原始值。

   * 与预期值相差（高出或低于）的百分比，该值由绿色实线表示。

   * 用于启动贡献分析的&#x200B;**[!UICONTROL 分析]**&#x200B;链接






