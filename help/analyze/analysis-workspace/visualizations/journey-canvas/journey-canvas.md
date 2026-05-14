---
description: 了解如何在 Analysis Workspace 中使用历程画布。
title: 历程画布概述
feature: Visualizations
role: User, Admin
source-git-commit: 0cc9ef6fda26aca07c7cae5496b2ba53fcbbb316
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 88%

---

# 历程画布概述 {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="历程画布"
>abstract="显示人们如何完成或退出一系列接触点。 用于具有多个入口点和路径的历程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="历程画布"
>abstract="分析人们如何完成或退出既定的历程。 创建由节点和箭头构成的灵活图表来代表事件、维度项和区段之间的任意组合，从而生成用户历程分析。 拖动画布上的节点来重新排列历程的事件和条件。 当您进行该操作时，数据会相应更新。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button2"
>title="历程画布"
>abstract="显示人们如何完成或退出一系列接触点。 用于具有多个入口点和路径的历程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel2"
>title="历程画布"
>abstract="分析人们如何完成或退出既定的历程。 创建由节点和箭头构成的灵活图表来代表事件、维度项和区段之间的任意组合，从而生成用户历程分析。 拖动画布上的节点来重新排列历程的事件和条件。 当您进行该操作时，数据会相应更新。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文在_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**&#x200B;中记录了历程画布可视化图表。<br/><br/>_&#x200B;对于本文的&#x200B;_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)_&#x200B;**Customer Journey Analytics**&#x200B;版本，请参阅[历程画布概述](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas)。_

>[!ENDSHADEBOX]

{{release-limited-testing}}

历程画布可视化图表可帮助您进行分析，获得关于您为用户和客户提供的历程的深入洞察。 它允许您定义历程，然后查看人员如何离开（流失）或继续通过（流过）历程。

您可以通过任意组合事件、维度项、区段和日期范围来创建历程节点，从而[构建用户历程分析](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。 通过连接各个节点来创建历程的流量，并包含多条路径和决策点。 拖动画布上的节点来重新排列历程的事件和条件。 当您进行更改时，数据会实时更新。

[节点已连接](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes)作为“最终路径”，这意味着只要访客最终从一个节点移动到另一个节点，就会计入访客，而不考虑两个节点之间发生的任何事件。 用户沿路径移动的时间由容器设置决定。

![历程画布](assets/journey-canvas.png)

## 主要功能

历程画布可视化图表的主要功能包括：

* 深入分析流失和流过情况，以适应最复杂的用户历程。

* 用于映射以及对用户历程的各个入口点、节点和路径进行可视化的画布。

* 通过拖放操作，将组件添加到画布上，并重新定位现有节点。

## 潜在洞察

历程画布可为最复杂的历程提供可操作洞察。

### 转化率最高的路径 {#conversion-rate-caption}

历程画布中最突出的洞察会以标题的形式在画布顶端显示。

此标题总结了历程中的哪些路径的转化率最高。

当历程中包含多个起始节点时，标题如下所示：

![历程画布洞察标题](assets/journey-canvas-caption.png)

当历程包含单个起始节点时，标题如下所示：

![历程画布洞察标题（单一起始节点）](assets/journey-canvas-caption-singlestart.png)

解释此标题时请考虑以下几点：

* _路径_&#x200B;被定义为由箭头连接的一个起始节点和一个终止节点，其间可连接任意数量的节点。

* 转化率的计算取决于历程的类型（历程中包含的起始节点和终止节点的数量，以及它们之间的路径是否相交）。

  下表描述了如何根据历程类型计算转换率：

  | 历程类型 | 转化率计算 | 示例 |
  |---------|----------|---------|
  | **单个起始节点和单个终止节点** | 转化率是通过将终止节点的数量除以起始节点的数量来计算的。 | ![有多个起点并汇聚到一个共同节点的历程](assets/journey-canvas-single-path.png) |
  | **单个起始节点和多个终止节点** | 转化率的计算方法是找到数值最高的终止节点，然后将该数字除以起始节点的数值。 | ![有多个起点并汇聚到一个共同节点的历程](assets/journey-canvas-singlestart-multiend.png) |
  | **多个独立路径，其中每个路径均包含一个起始节点和一个终止节点** | 转化率是通过将终止节点的数量除以起始节点的数量来计算的。 标题中描述了转化率最高的路径。 | ![有多个起点并汇聚到一个共同节点的历程](assets/journey-canvas-multi-start-separate.png) |
  | **在历程中的任何一点，汇聚到一个共同的节点的多个起始节点** | 转化率的计算方法是找到数值最高的终止节点，并将该数字除以具有最低数值的开始节点的数值来计算的。 | ![有多个起点并汇聚到一个共同节点的历程](assets/journey-canvas-multi-start-converge.png) |

### 流过、流失等

以下是历程画布可帮助提供的其他洞察的几个示例。 您可以选择这些见解是基于报表包中的所有人员、所有开始历程的人员还是历程之前节点的所有人员。

#### 流过

* 完成历程（到达终止节点）的人数和百分比

* 到达历程中某一节点的人数和百分比

* 在历程的某个给定节点之前或之后最常见的步骤

#### 流失

* 在历程中，人们最常流失（即从未到达任何紧邻的下一个节点）的节点

#### 每个节点的附加数据

* 在历程的任何节点上添加一个细分维度，以查看该特定节点的其他数据

## 在“历程画布”、“流失”或“流量”可视化图表之间进行选择

历程画布可视化图表与[流失可视化图表](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)和[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)有相似之处，但也存在重要区别。

### 了解这些差异

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何时使用历程画布

历程画布对于以下方面至关重要：

* 涉及具有多个入口点和路径的历程的流失分析。

* 具有多个入口点和路径的非线性历程，其中带有预定义的页面序列。

* 基于预定义历程的探索性、临时性分析。

* 需要除会话、人员或发生次数之外的主要量度的分析。

使用[上述表格](#understand-the-differences)来了解历程画布、流失和流量可视化图表之间的区别。

## 在历程画布中构建分析

您可以在历程画布中构建基于 Analysis Workspace 中可用的任何维度或量度的分析。 有关详细信息，请参阅[配置历程画布可视化图表](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。


>[!MORELIKETHIS]
>
> * [Adobe Customer Journey Analytics 中的历程画布可视化图表指南](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

