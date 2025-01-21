---
title: 区段比较面板概述
description: 了解如何使用“区段比较”面板（Analysis Workspace 中区段 IQ 的一部分）。
keywords: Analysis Workspace;区段 IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: 2aaa8c0d13755b40ec701ca6342ab773103a0422
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 27%

---

# 区段比较面板概述 {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="区段比较"
>abstract="对所有数据点快速比较两个区段，以自动查找相关差异。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="区段比较面板"
>abstract="对所有数据点快速比较两个区段，以自动查找相关差异。<br/><br/>**参数&#x200B;**<br/>**添加区段**：要分析的第一个区段。<br/>**与**&#x200B;比较：要与之比较的第二个区段。 这将自动使用&#x200B;*Everyone Else*&#x200B;填充，这与您的第一个区段相反。 如果需要，可以使用其他区段替换它。<br/>**高级设置**：在区段比较中排除要分析的组件的功能。"
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的区段比较面板。_<br/>_在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中没有等效面板。_

>[!ENDSHADEBOX]

区段比较面板是[区段 IQ](../../segment-iq.md) 中的一个工具，可以发现无限数量的区段中最具统计意义的差异。该功能通过自动分析您有权访问的所有维度和量度来进行迭代。它会自动找出受众区段中可提升公司 KPI 的关键特征，并让您了解任意区段的重叠程度。

+++ 以下是一段关于区段比较的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23976/?quality=12)

+++

## 使用

要使用&#x200B;**[!UICONTROL 归因]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 归因]**&#x200B;面板。 有关如何创建面板的信息，请参阅[创建面板](../panels.md#create-a-panel)。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。



### 面板输入

您可以使用以下输入设置配置[!UICONTROL 区段比较]面板：

![区段比较输入面板](assets/segment-comparison-input.png)

| 输入 | 描述 |
| --- | --- |
| **[!UICONTROL 添加区段]** | 选择要比较的维。 |
| **[!UICONTROL 与]**&#x200B;比较 | 选择要用于比较初始选定区段的维度。 如果不选择特定区段，则使用默认区段&#x200B;**[!UICONTROL 其他各项]**。 |
| **[!UICONTROL 显示/隐藏高级设置]** | 选择&#x200B;**[!UICONTROL 显示高级设置]**&#x200B;以配置&#x200B;**[!UICONTROL 排除的组件]**，选择&#x200B;**[!UICONTROL 隐藏高级设置]**&#x200B;以隐藏&#x200B;**[!UICONTROL 排除的组件]**。 |
| **[!UICONTROL 排除的组件]** | 您可以指定的组件，如&#x200B;**[!UICONTROL Dimension]**、**[!UICONTROL 指标]**&#x200B;或排除的&#x200B;**[!UICONTROL 区段]**。<br><ul><li>将容器中的一个或多个维度、量度或区段拖放到&#x200B;**[!UICONTROL 排除的组件]**&#x200B;容器中。</li><li>要删除组件，请选择类型(**[!UICONTROL Dimension]** **[!UICONTROL 指标]**&#x200B;或&#x200B;**[!UICONTROL 区段]**)，然后选择![交叉大小75](/help/assets/icons/CrossSize75.svg)以删除组件。 要删除所有组件，请选择&#x200B;**[!UICONTROL 全部清除]**。</li><li>要将维度、量度和区段的当前选择设置为默认值，请选择&#x200B;**[!UICONTROL 设置为默认值]**。</li></ul> |

选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

### 面板输出

在Adobe Analytics完成对两个所需区段的分析后，输出面板会通过多种可视化图表显示结果：

![面板输出区段比较](assets/segment-comparison-output.png)

| 可视化图表 | 描述 |
|---|---|
| **[!UICONTROL 大小和重叠]** | 通过[维恩图](/help/analyze/analysis-workspace/visualizations/venn.md)可视化图表说明每个选定区段的比较大小以及它们彼此重叠的程度。 |
| 第1区段的&#x200B;**[!UICONTROL 独特访客]** | 显示第一个区段独特访客的[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表（在单页面访问量示例中） |
| 第2个区段的&#x200B;**[!UICONTROL 独特访客]** | 显示第二个区段（在首次访问示例中）独特访客的[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表 |
| 针对区段&#x200B;**[!UICONTROL 排名最前的量度]** | 显示选定区段排名最前的[自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 |
| **[!UICONTROL 一段时间内的量度（按区段）]** | 显示一段时间内选定区段量度的[折线图](/help/analyze/analysis-workspace/visualizations/line.md)可视化图表。 |
| 针对区段&#x200B;**[!UICONTROL 排名最前的维度项目]** | 显示选定区段混合维度项的[自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 |
| 按区段&#x200B;**[!UICONTROL Dimension项目]** | 一个[水平条形图](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)可视化图表，按区段显示维度项目。 |
| 针对区段&#x200B;**[!UICONTROL 排名最前的区段]** | 一个[自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)，它针对区段显示排名最前的区段。 |
| **[!UICONTROL 区段重叠]** | 显示区段重叠的[维恩图](/help/analyze/analysis-workspace/visualizations/venn.md)可视化图表。 |

使用![编辑](/help/assets/icons/Edit.svg)重新配置并重新构建面板。


<!--
#### Size and overlap

Illustrates the comparative sizes of each selected segment and how much they overlap with each other using a venn diagram. You can hover over the visual to see how many visitors were in each overlapping or non-overlapping section. You can also right click on the overlap to create a brand new segment for further analysis. If the two segments are mutually exclusive, no overlap is shown between the two circles (typically seen with segments using a hit container).

![Size and overlap](assets/size-overlap.png)

#### Population summaries

To the right of the Size and Overlap visualization, the total unique visitor count in each segment and overlap is shown.

![Population summaries](assets/population_summaries.png)

#### Top metrics

Displays the most statistically significant metrics between the two segments. Each row in this table represents a differentiating metric, ranked by how different it is between each segment. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific metric is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific metric. If a metric is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Metrics added to this table after the segment comparison has finished do not receive a Difference Score.

![Top metrics](assets/top-metrics.png)

#### Metric over time by segment

To the right of the metrics table is a linked visualization. You can click a line item in the table on the left, and this visualization updates to show that metric trended over time.

![Top metrics line](assets/linked-viz.png)

#### Top dimensions

Shows the most statistically significant dimension items across all of your dimensions. Each row shows the percentage of each segment exhibiting this dimension item. For example, this table might reveal that 100% of visitors in 'Segment A' had the dimension item 'Browser Type: Google', whereas only 19.6% of 'Segment B' had this dimension item. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific dimension item is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific dimension item. If a dimension item is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Dimension items added to this table after the segment comparison has finished do not receive a Difference Score.

![Top dimensions](assets/top-dimension-item1.png)

#### Dimension items by segment

To the right of the dimensions table is a linked bar chart visualization. It shows all displayed dimension items in a bar chart. Clicking a line item in the table on the left updates the visualization on the right.

![Top dimensions bar chart](assets/top-dimension-item.png)

#### Top segments

Shows which other segments (other than the two segments selected for comparison) have statistically significant overlap. For example, this table can show that a third segment, 'Repeat Visitors', overlaps highly with 'Segment A' but does not overlap with 'Segment B'. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific segment is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific segment. If a segment is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Segments added to this table after the segment comparison has finished do not receive a Difference Score.

![Top segments](assets/top-segments.png)

#### Segment overlap

To the right of the segments table is a linked venn diagram visualization. It shows the most statistically significant segment applied to your compared segments. For example, 'Segment A' + 'Statistically significant segment' vs. 'Segment B' + 'Statistically significant segment'. Clicking a segment line item in the table on the left updates the venn diagram on the right.

![Top segments venn diagram](assets/segment-overlap.png)

-->
