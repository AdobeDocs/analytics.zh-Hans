---
description: 让您轻松地在 Analysis Workspace 中进行数据的可视化比较，例如构建与上个月、去年等的比较。
title: 组合图表可视化
feature: Visualizations
role: User, Admin
exl-id: 08e49857-aa58-4527-bdfd-b1663a75a02b
source-git-commit: 8234da343ed526eced900e24225e2e1af4319a4d
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 48%

---

# 组合图表 {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="组合"
>abstract="快速创建可视化组合图表，无需先创建自由格式表。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._中的组合可视化图表

_查看本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本的[组合](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts)。_

>[!ENDSHADEBOX]


通过![组合图表](/help/assets/icons/ComboChart.svg) **[!UICONTROL 组合图表]**&#x200B;可视化图表，可以轻松快速地构建比较可视化图表，而无需先构建表格。 您可以通过线条/条形组合轻松查看数据趋势。

使用[!UICONTROL 组合]可以：

* 将本周的订单与上个月（和去年）同一时间的订单进行比较。
* 在同一张图表上快速分析和比较多个量度（如[!UICONTROL 人员]和[!UICONTROL 收入]）。
* 在一段时间内针对某个函数（例如[!UICONTROL 累积平均数]）分析量度。

请记住以下事项：

* 您可以在单个[!UICONTROL 组合图表]中添加多个比较。
* 如果添加一个或多个比较，则它们必须是同一类型，例如[!UICONTROL 时间比较]。
* 最多可添加 5 个比较。
* 您最多可以为一个量度应用3个过滤器。
* 组合图表中不支持计算指标。

## 使用

1. 添加![评论](/help/assets/icons/ComboChart.svg) [!UICONTROL 组合]可视化图表。 查看[将可视化图表添加到面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. 从下拉列表中，为 X 轴选择一个维度，为 Y 轴选择一个量度。

1. 选择要使用的[!UICONTROL 线形比较]的类型。

   | 线形比较类型 | 定义 |
   | --- | --- |
   | **[!UICONTROL 时间比较]** | 最常见的比较类型 – 例如，将此时间段与 4 周前进行比较。如果您选择了[!UICONTROL 时间比较]，则对要比较的时间段进行二次选择。<p>![与选定时段和选定时段的辅助选择字段进行比较。](assets/combo-time-period.png) |
   | **[!UICONTROL 函数]** | 您可以在比较中引入函数（例如[!UICONTROL 平均值]）。查看[支持的函数的列表](#supported-functions)。<p>![LIne比较下拉菜单，其中显示选定函数和可用受支持函数的列表。](assets/combo-functions.png) |
   | **[!UICONTROL 辅助量度]** | 例如，您可以将[!UICONTROL 收入]与另一个量度进行比较。<p>![比较两个量度的组合图表。](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. 选择&#x200B;**[!UICONTROL 生成]**。

   输出类似于：

   ![在条形图中显示当前时段的组合图表，在折线图](assets/combo-output.png)中显示比较时段

   当前期间显示在条形图中。 折线图表示比较时段。 折线图上的点称为&#x200B;*条形铃*。

## 支持的函数

如果选择&#x200B;**[!UICONTROL Function]**&#x200B;作为[!UICONTROL Line比较类型]，则会返回所选量度的函数。

| 函数 | 定义 |
| --- | --- |
| **[!UICONTROL 列总和]** | 添加列中某指标的所有数值（跨维度元素） |
| **[!UICONTROL 累积平均数]** | 返回最后N行的平均值。 |
| **[!UICONTROL 中间值]** | 返回列中某量度的中间值。中间值是位于一组数字中间的数字。一半数字的值大于或等于中间值，另一半数字的值小于或等于中间值。 |
| **[!UICONTROL 累积数]** | N 行的累积总和。 |
| **[!UICONTROL 列最大值]** | 返回某量度列的一组维度元素中的最大值。 |
| **[!UICONTROL 平均值]** | 返回某度量的算术平均值或平均值。 |
| **[!UICONTROL 列最小值]** | 返回某量度列的一组维度元素中的最小值。 |

{style="table-layout:auto"}

以下是“收入”量度的累积平均值的示例：

![显示累积平均值的组合图表](assets/combo-cumul-avg.png)

以下是使用了累积平均值和均值函数的组合图表的示例：

![显示累积平均和平均函数的组合图表。](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化设置](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化上下文菜单](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
