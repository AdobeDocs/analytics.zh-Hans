---
title: 区段比较面板概述
description: 了解如何使用Analysis Workspace中的“区段比较”面板。
keywords: Analysis Workspace;区段 IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: 810e52260443ccc076e07b8d638563d56db9956e
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 64%

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
>title="“区段比较”面板 "
>abstract="对所有数据点快速比较两个区段，以自动查找相关差异。<br/><br/>**参数&#x200B;**<br/>**添加区段**：要分析的第一个区段。<br/>**与**&#x200B;进行比较：要与之比较的第二个区段，将自动使用&#x200B;*其他各项*&#x200B;填充该区段（与第一个区段相反）。 如果需要，您可以使用其他区段替换&#x200B;*其他各项*。<br/>**高级设置**：在区段比较中能够排除被分析的组件。"
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中的区段比较面板。_<br/>__![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 中没有等效面板。_

>[!ENDSHADEBOX]

区段比较面板可发现无限数量的区段中最具统计意义的差异。 该功能通过自动分析您有权访问的所有维度和量度来进行迭代。它会自动找出受众区段中可提升公司KPI的关键特征，并让您查看区段重叠程度。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [区段比较](https://video.tv.adobe.com/v/23976?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]



## 使用

要使用&#x200B;**[!UICONTROL 归因]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 归因]**&#x200B;面板。有关如何创建面板的信息，请参阅[创建面板](../panels.md#create-a-panel)。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。



### 面板输入

可以使用以下输入设置配置[!UICONTROL 区段比较]面板：

![区段比较输入面板](assets/segment-comparison-input.png)

| 输入 | 描述 |
| --- | --- |
| **[!UICONTROL 添加区段]** | 选择要与之比较的维。 |
| **[!UICONTROL 比较参照对象]** | 选择要用于比较初始选定区段的维度。 如果您未选择特定区段，则将使用默认区段&#x200B;**[!UICONTROL 其他各项]**。 |
| **[!UICONTROL 显示/隐藏高级设置]** | 选择&#x200B;**[!UICONTROL 显示高级设置]**&#x200B;以配置&#x200B;**[!UICONTROL 排除的组件]**，选择&#x200B;**[!UICONTROL 隐藏高级设置]**&#x200B;以隐藏&#x200B;**[!UICONTROL 排除的组件]**。 |
| **[!UICONTROL 排除的组件]** | 您可以指定的组件，例如&#x200B;**[!UICONTROL 维度]**、**[!UICONTROL 量度]**&#x200B;或&#x200B;**[!UICONTROL 区段]**&#x200B;以供排除。<br><ul><li>将一个或多个维度、量度或区段从容器拖放到&#x200B;**[!UICONTROL 排除的组件]**&#x200B;容器。</li><li>要移除组件，请选择类型（**[!UICONTROL 维度]**、**[!UICONTROL 量度]**&#x200B;或&#x200B;**[!UICONTROL 区段]**），并选择 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 以移除组件。要移除所有组件，请选择&#x200B;**[!UICONTROL 全部清除]**。</li><li>要将当前选择的维度、量度和区段设置为默认选项，请选择&#x200B;**[!UICONTROL 设为默认值]**。</li></ul> |

选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

### 面板输出

Adobe Analytics完成对两个所需区段的分析后，输出面板将通过多个可视化图表显示结果：

![面板输出区段比较](assets/segment-comparison-output.png)

| 可视化图表 | 描述 |
|---|---|
| **[!UICONTROL 大小和重叠]** | 使用[维恩图](/help/analyze/analysis-workspace/visualizations/venn.md)可视化图表说明每个选定区段的比较大小以及它们彼此重叠的程度。 |
| **[!UICONTROL 第一区段的独特访客量]** | 显示第一个区段（例如单页面访问量）独特访客的[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表 |
| **[!UICONTROL 第二区段的独特访客量]** | 显示第二个区段（例如第一次访问）独特访客的[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表 |
| 针对区段&#x200B;**[!UICONTROL 排名最前的量度]** | [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)显示选定区段的热门量度。 |
| **[!UICONTROL 按区段划分随时间变化的量度]** |  [线形图](/help/analyze/analysis-workspace/visualizations/line.md)可视化图表显示选定区段随时间变化的量度。 |
| **[!UICONTROL 针对区段的热门维度项]** | [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)显示选定区段的混合维度项。 |
| **[!UICONTROL 按区段划分的维度项]** | [水平条形图](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)可视化图表按区段划分显示维度项。 |
| **[!UICONTROL 针对区段的热门区段]** | [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)显示针对区段的热门区段。 |
| **[!UICONTROL 区段重叠]** | [维恩图](/help/analyze/analysis-workspace/visualizations/venn.md)可视化图表显示区段重叠。 |

使用![编辑](/help/assets/icons/Edit.svg)重新配置并重新生成面板。


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
