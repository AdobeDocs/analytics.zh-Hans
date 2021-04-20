---
description: 以可视化方式直观地展示您的数据。
keywords: Analysis Workspace
title: 可视化图表概述
feature: Visualizations
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 42%

---


# 可视化图表概述

工作区提供了许多可视化图表，使您能够生成数据的可视化表示形式，如条形图、圆环图、直方图、折线图、地图、散点图等。如果您使用Adobe Analytics，大多数可视化类型都将为您所熟悉。 但是，Analysis Workspace 提供了可视化图表设置，以及许多全新或独特的具有交互功能的可视化图表类型。

您可以从Workspace中左上角的图标、[空白面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=zh-Hans)或通过工作流中的右键单击菜单访问可视化。

![](assets/viz-rail.png)

Analysis Workspace中提供以下可视化类型：

| 可视化图表名称 | 描述 |
| --- | --- |
| [面积图](/help/analyze/analysis-workspace/visualizations/area.md) | 就像线图，但线下有彩色区域。 当您有多个量度并且希望显示两个或更多量度相交的区域时，可使用面积图。 |
| [条形图](/help/analyze/analysis-workspace/visualizations/bar.md) | 显示一些垂直条，这些垂直条表示一个或多个量度中的各种值。 |
| [项目符号图表](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | 显示您感兴趣的值与其他性能范围（目标）进行比较或衡量的结果。 |
| [同类群组表](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | *`cohort`* 是指一组在特定期限内共享相同特性的人员。同期群分析对保留、参与或延迟分析很有用。 |
| [圆环](/help/analyze/analysis-workspace/visualizations/donut.md) | 此可视化图表与饼图类似，它将数据显示为整体的一部分或区段。 |
| [流失](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | 流失报表显示访客从何处离开（流失）或继续通过（流过）预定义的页面序列。可以设置为最终或精确序列 |
| [流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | 显示您网站和应用程序中的准确客户路径。 |
| [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) | 自由格式表不仅可以作为数据表，而且还是一个交互式可视化图表。它是Workspace中数据分析的基础。 |
| [直方图](/help/analyze/analysis-workspace/visualizations/histogram.md) | 直方图时段访客、访问量或基于量度卷的时段点击量。 |
| [水平条](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | 显示一些水平条，这些水平条表示一个或多个量度中的各种值。 |
| [折线图](/help/analyze/analysis-workspace/visualizations/line.md) | 使用线条来表示量度，以显示一段时间内值的变化情况。折线图沿x轴使用时间。 |
| [地图](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | 允许您构建任何量度（包括计算量度）的可视地图。 |
| [散点图](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | 显示维度项目与最多三个量度之间的关系。 |
| [概要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 将所选单元格显示为1个大数。 |
| [概要变化](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 以1大数字/百分比的形式显示选定单元格之间的更改。 |
| [文本](/help/analyze/analysis-workspace/visualizations/text.md) | 允许您将用户定义的文本添加至您的工作区。除了利用面板/可视化描述外，还有助于为分析和洞察添加更多上下文 |
| [树图](/help/analyze/analysis-workspace/visualizations/treemap.md) | 将分层（树结构）数据显示为一组嵌套的矩形。 |
| [维恩图](/help/analyze/analysis-workspace/visualizations/venn.md) | 使用圆描述最多3个区段的量度重叠。 |

## 设置 {#settings}

每个可视化图表都有其自身的设置，您可以管理这些设置。要访问[!UICONTROL 可视化设置]，请单击[!UICONTROL 可视化设置]齿轮图标。

![](assets/settings.png)

| 设置 | 描述 |
| --- | --- |
| 可视化类型 | 更改用于描述数据的可视类型。 |
| 粒度 | 对于趋势可视化，您可以更改时间粒度（天、周、月等） 。 此更改也适用于数据源表。 |
| 百分数 | 显示百分数值。 |
| 100% 堆叠 | 堆叠区域、堆叠条形或堆叠水平条形可视化上的此设置会将图表转换为“100%堆叠”可视化。 示例：![堆叠100%](assets/stacked_100_percent.png) |
| 图例可见 | 用于隐藏“摘要编号/摘要更改”可视化的详细图例文本。 |
| 限制最大项目数 | 允许您限制可视化图表显示的项目数量。 |
| 将 Y 轴定位为 0 | 如果图表上绘制的所有值都远远大于零，则图表默认会将 y 轴底部设置为非零值。如果选中此框，y 轴将被强制设置为零（并将重新绘制图表）。 |
| 标准化 | 要求所有量度按等比例计算。当绘制的量度大小非常不同时，这非常有用。 |
| 显示双轴 | 仅适用于具有两个量度的情况，可以在左（用于一个量度）、右（用于另一个量度）两边各有一个 y 轴。当绘制的量度大小非常不同时，这非常有用。 |
| 显示异常 | 通过显示异常检测功能来增强线形图和自由格式表。 线形可视化中的异常检测包括预期值（虚线）和预期范围（阴影带）。 |

## 图例 {#legend}

可视化图例可帮助您将源表中的日期与可视化中绘制的系列关联起来。 图例是交互式的 — 您可以单击图例项来显示/隐藏可视化中的系列。 如果您希望简化可视化数据，则此功能非常有用。

此外，您还可以重命名图例标签，以帮助您使视觉元素更易于消费。 注意：图例编辑&#x200B;****&#x200B;不适用于：树图、项目符号、摘要更改/数量、文本、自由形式、直方图、同期群或流可视化。

要编辑图例标签：

1. 右键单击某个图例标签。
1. 单击&#x200B;**[!UICONTROL 编辑标签]**。

   ![](assets/edit-label.png)

1. 输入新的标签文本。
1. 按 **[!UICONTROL Enter]** 键保存。

下面是一个[指向该主题相关视频的链接](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html)。

## 右键单击菜单{#right-click}

右键单击可视化标题即可获得可视化的其他功能。 设置将因可视化而异。 一些可用设置包括：

![](assets/right-click.png)

| 设置 | 描述 |
| --- | --- |
| 插入复制的面板/可视化 | 允许您将复制的面板或可视化粘贴（“插入”）到项目中的其他位置或完全不同的项目中。 |
| 复制可视化 | 允许您右键单击并复制可视化，以便将其插入到项目中的其他位置或完全不同的项目中。 |
| [以 CSV 格式下载项目](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-items) | 以CSV形式下载所选维度的最多50,000个维度项目。 |
| [将数据下载为 CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-data) | 以CSV格式下载可视化数据源。 |
| 复制可视化 | 生成一个与当前可视化图表完全相同的副本，然后可对其进行修改。 |
| 编辑描述 | 添加（或编辑）可视化的文本描述。 |
| 获取可视化图表链接 | 允许您将某人定向到项目中的特定可视化。 单击链接后，收件人需要先登录，然后才能定向到链接到的确切可视化。 |
| 重新开始 | （适用于流、维恩、直方图）删除当前可视化的配置，以便您可以从头重新配置它。 |

## “创建可视化”图标 {#quick-viz}

如果您不确定要选择哪个可视化，请单击任何表行（悬停时可用）中的&#x200B;**[!UICONTROL 创建Visual]**&#x200B;图标。 这是添加可视化的最快方法。 单击此图标将提示 Analysis Workspace 针对哪种可视化图表最适合您的数据做出有根据的推测。例如，如果选择了1行，则将创建趋势线图。 如果您选择了3个区段行，它将创建一个维恩图。

![](assets/quick-viz.png)
