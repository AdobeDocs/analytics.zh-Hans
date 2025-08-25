---
description: 了解如何使用Analysis Workspace中提供的可视化图表直观地表示您的数据。
keywords: Analysis Workspace
title: 可视化概述
feature: Visualizations
role: User, Admin
exl-id: b40aa942-4a08-4ff3-9895-e92f9a187b54
source-git-commit: 8d9323be962b85a278a61be34f176c82e3f9b1c4
workflow-type: tm+mt
source-wordcount: '1707'
ht-degree: 88%

---

# 可视化内容概述

工作区提供了多种可视化工具，可帮助您生成数据的可视化表示。例如条形图、环形图、直方图、线形图、地图、散点图等。

## 类型

Analysis Workspace 中提供了以下可视化图表类型：


| 图标 | 名称 | 描述 |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [面积图](/help/analyze/analysis-workspace/visualizations/area.md) | 面积图可视化。与线形图相似，但线条下有彩色区域。当您有多个量度并且希望显示两个或更多量度相交的区域时，可以使用面积图。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [条形图](/help/analyze/analysis-workspace/visualizations/bar.md) | 一种条形图可视化，其中垂直条表示一个或多个量度的不同值。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [堆积条形图](/help/analyze/analysis-workspace/visualizations/bar.md) | 一种堆积条形图可视化，其中垂直条表示一个或多个量度的不同值。 |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [项目符号](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | 子弹图可视化，显示您感兴趣的值与其他性能范围（目标）的比较或衡量情况。 |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [同类群组表](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 同类群组可视化是指一组在特定期限内共享相同特性的人员。同类群组表对于保留、流失或延迟分析非常有用。 |
| ![组合](/help/assets/icons/ComboChart.svg) | [组合](combo-charts.md) | 组合图表使您无需先构建表格，即可快速构建比较可视化图表。 |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [环形图](/help/analyze/analysis-workspace/visualizations/donut.md) | 与饼图类似，可视化圆环图将数据展示为整体的各个部分或区段。 |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [流失](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | 流失可视化图表展示了用户在预定义的页面顺序中离开（流失）和继续浏览（流过）的情况。 |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [流](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | 流量可视化展示了客户通过您的网站和应用程序的具体路径。 |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) | 自由格式表可视化是一种互动式可视化工具。自由格式表可视化是工作区中数据分析的基础。 |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [直方图](/help/analyze/analysis-workspace/visualizations/histogram.md) | 直方图可视化根据量度的量级将人员、访问或事件分入不同的桶中。 |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [水平条](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | 水平条可视化显示了一些水平条，这些水平条表示一个或多个量度中的各种值。 |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [堆叠的水平条形图](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | 堆叠水平条形图可视化展示了代表一个或多个量度不同值的水平条。 |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [关键量度摘要](/help/analyze/analysis-workspace/visualizations/key-metric.md) | 关键量度摘要可视化结合了线形图、摘要变化图和摘要数字可视化。 |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Line](/help/analyze/analysis-workspace/visualizations/line.md) | 线形图可视化图表使用线条来表示量度，以显示一段时间内值的变化情况。将时间作为 x 轴的线形图。 |
| ![地球](/help/assets/icons/Globe.svg) | [地图](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | 允许您构建任何量度（包括计算量度）的可视地图 |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散点图](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | 散点图可视化图表显示维度项与最多三个量度之间的关系。 |
| ![PageRule](/help/assets/icons/PageRule.svg) | [部分标头](section-header.md) | 识别并阐述面板中的各个部分。 |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [摘要变化](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 摘要变化可视化将所选单元格之间的变化显示为一个大的数字或百分比。 |
| ![ 123](/help/assets/icons/123.svg)</p> | [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 摘要数字可视化将选定的单元格显示为一个大的数字。 |
| ![Text](/help/assets/icons/Text.svg) | [文本](/help/analyze/analysis-workspace/visualizations/text.md) | 文本可视化功能允许您将用户定义的文本添加到工作区。在利用面板/可视化图表描述之外，对于向您的分析和洞察添加额外的上下文非常有用 |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [树状图](/help/analyze/analysis-workspace/visualizations/treemap.md)<p> | 树状图可视化将层次化（树状结构）数据显示为一组嵌套的矩形。 |
| ![Type](/help/assets/icons/TwoDots.svg) | [维恩图](/help/analyze/analysis-workspace/visualizations/venn.md) | 可视化维恩图使用圆圈来描绘最多 3 个区段的量度重叠。 |

<!--

| Name| Icon | Description |
| --- |:---: | ---|
| [Area](/help/analyze/analysis-workspace/visualizations/area.md)|![Area icon](assets/Smock_GraphArea_18_N.svg)</p> | Like a line graph, but with a colored area below the line. Use an area graph when you have multiple metrics and want to visualize the area expressed by the intersection of two or more metrics. |
| [Bar](/help/analyze/analysis-workspace/visualizations/bar.md)|![Bar icon](assets/Smock_GraphBarVertical_18_N.svg)</p> | Shows vertical bars representing various values across one or more metrics. |
| [Bullet graph](/help/analyze/analysis-workspace/visualizations/bullet-graph.md)|![Bullet icon](assets/Smock_GraphBullet_18_N.svg)</p> | Shows how a value you are interested in compares to or measures against other performance ranges (goals). |
| [Cohort table](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)|![Cohort table icon](assets/Smock_TextNumbered_18_N.svg)</p> | A *`cohort`* is a group of people sharing common characteristics over a specified period. Cohort Analysis is useful for retention, churn or latency analysis. |
| [Donut](/help/analyze/analysis-workspace/visualizations/donut.md) | ![Donut icon](assets/Smock_GraphDonut_18_N.svg)</p> | Similar to a pie chart, this visualization shows data as parts or segments of a whole. |
| [Fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | ![Fallout icon](assets/Smock_ConversionFunnel_18_N.svg)</p> | Fallout reports show where visitors left (fell out) and continued through (fell through) a predefined sequence of pages. Can be set to eventual or exact sequences |
| [Flow](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | ![Flow icon](assets/flow-icon.png)</p> | Shows exact customer paths through your websites and apps. |
| [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) | ![Freeform table icon](assets/Smock_ViewTable_18_N.svg)</p> | A Freeform table is not merely a data table, but also an interactive visualization. It is the foundation for data analysis in Workspace.|
| [Histogram](/help/analyze/analysis-workspace/visualizations/histogram.md) | ![Histogram icon](assets/Smock_GraphHistogram_18_N.svg)</p> | A histogram buckets visitors, visits or hits into buckets based on a metric volume. |
| [Horizontal bar](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | ![Horizontal bar icon](assets/Smock_GraphBarHorizontal_18_N.svg)</p> | Shows horizontal bars representing various values across one or more metrics. |
| [Key metric summary](/help/analyze/analysis-workspace/visualizations/key-metric.md) | ![Key metric icon](assets/key-metric-icon.png)</p> | Shows how a metric is trending within a single timeframe, or lets you compare metric performance across two timeframes. |
| [Line](/help/analyze/analysis-workspace/visualizations/line.md) | ![Line icon](assets/Smock_GraphTrend_18_N.svg)</p> | Represents metrics using a line in order to show how values change over a period of time. A line chart uses time along the x-axis. |
| [Map](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | ![Map icon](assets/map-icon.png)</p> | Lets you build a visual map of any metric (including calculated metrics). |
| [Scatterplot](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | ![Scatterplot icon](assets/Smock_GraphScatter_18_N.svg)</p> | Shows the relationship between dimension items and up to three metrics. |
| [Summary number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | ![Summary number icon](assets/summary-number-icon.png)</p> | Shows the selected cell as 1 large number. |
| [Summary change](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | ![Summary change icon](assets/summary-change-icon.png)</p> | Shows the change between the selected cells as 1 large number/percent. |
| [Text](/help/analyze/analysis-workspace/visualizations/text.md) | ![Text icon](assets/Smock_Text_18_N.svg)</p> | Lets you add user-defined text to your Workspace. Helpful for adding additional context to your analysis and insights, in addition to leveraging panel/visualization descriptions |
| [Treemap](/help/analyze/analysis-workspace/visualizations/treemap.md) | ![Treemap icon](assets/Smock_GraphTree_18_N.svg)</p> | Displays hierarchical (tree-structured) data as a set of nested rectangles. |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) | ![Venn icon](assets/venn-icon.png)</p> | Uses circles to depict the metric overlap of up to 3 segments. |

-->

## 将可视化图表添加到面板

1. 打开您想要添加可视化图表的 Analysis Workspace 项目。

1. 使用以下任一方法添加可视化图表：

   ![添加可视化图表](assets/add-visualization.png)

   * 在左侧面板中，选择 ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) **可视化图表**，然后将可视化图表拖至要添加可视化图表的面板中。

   * 在要添加可视化图表的面板上，选择 ![AddCircle](/help/assets/icons/AddCircle.svg)，然后选择代表要添加的可视化图表的图标。将光标悬停在每个可视化图表的图标上，即可查看其名称。

   * 添加[空白面板](/help/analyze/analysis-workspace/c-panels/blank-panel.md)，然后选择要添加的可视化图表。

   * 从 Analysis Workspace 项目现有可视化图表的上下文菜单中，选择&#x200B;**[!UICONTROL 重复可视化图表]**&#x200B;或&#x200B;**[!UICONTROL 复制可视化图表]**。

   * 使用工作区&#x200B;**[!UICONTROL 插入]**&#x200B;菜单插入可视化图表。

   * 从自由格式表的上下文菜单中，选择&#x200B;**[!UICONTROL 可视化图表]**。然后，从子菜单中选择可视化图表。根据表中的当前选择，工作区会确定提供哪种可视化图表，并解释数据以生成所请求的可视化图表。

添加简单的可视化图表，例如[条形图](line.md)的[折线图](bar.md)可视化图表时，该可视化图表使用最接近的自由格式表作为数据源。 您始终可以修改可视化图表的[数据源](#data-source)。

## 管理可视化图表

当您将鼠标悬停在可视化图表上或选择可视化图表时，可以管理该可视化图表。

![管理可视化图表](assets/manage-visualization.png)

* 要折叠可视化图表，请选择![V形向下](/help/assets/icons/ChevronDown.svg)。
* 要显示折叠的可视化图表，请选择![V形左侧](/help/assets/icons/ChevronLeft.svg)。
* 要删除可视化图表，请选择![CrossSize400](/help/assets/icons/CrossSize400.svg)。 要撤消操作，请选择&#x200B;**[!UICONTROL 编辑]** > **[!UICONTROL 撤消]** (**[!UICONTROL *cmd+z *]**) |**[!UICONTROL * ctrl+z *]**)。
* 要将可视化返回到默认高度，请选择![ImageResize](/help/assets/icons/Resize.svg)。
* 要在面板中移动可视化图表，请在![移动](/help/assets/icons/Move.svg)可见时拖放该可视化图表（通常是将鼠标悬停在标题上）。


## 图例

可视化图表图例可帮助您将源表中的日期与可视化图表中绘制的系列关联起来。图例是交互式的 - 您可以选择图例项来显示/隐藏可视化图表中的一个系列，如果您想简化可视化图表的数据，这将很有帮助。

此外，可以重命名图例标签，这样有助于更好地使用视觉效果。注意：图例编辑&#x200B;**不会**&#x200B;应用到：树状图、项目符号、概要变化/概要数字、文本、自由格式表、直方图、同类群组或流可视化图表。

要编辑图例标签，请执行以下操作：

1. 右键单击某个图例标签。
1. 单击&#x200B;**[!UICONTROL 编辑标签]**。

   ![图例标签和编辑标签选项。](assets/edit-label.png)

1. 输入新的标签文本。
1. 按 **[!UICONTROL Enter]** 键保存。


## 设置

每个可视化图表都有其自己的设置。要访问可视化设置，请选择可视化标头中的 ![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 设置]**&#x200B;以显示弹出窗口。

根据可视化效果，您可以配置

* 可视化数据来源的详细信息（通过[**[!UICONTROL 数据源]**](#data-source)选项卡进行配置），以及
* 可视化设置（通过[**[!UICONTROL 设置]**](#settings-1)选项卡进行配置）。

![可视化设置](assets/visualization-settings.png)

### 数据源

您可以控制哪个数据源以及该数据源中的哪些项目或位置与可视化相对应。请参阅[管理数据源](t-sync-visualization.md)，以了解详细信息。

### 设置

可视化图表决定了哪些可视化图表设置可用。下表总结了最常见的设置。某些可视化图表确实有特定设置。有关更多详细信息，请参阅单个可视化图表文档。

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 可视化类型]** | 更改用于显示数据的可视化图表类型。 |
| **[!UICONTROL 粒度]** | 更改趋势性可视化图表的时间粒度。此更改也适用于数据源表。 |
| **[!UICONTROL 百分比]** | 显示百分比值。 |
| **[!UICONTROL 100% 堆叠]** | 将图表转变为 100% 堆叠的可视化图表。仅适用于面积图、条形图和水平堆叠的条形图可视化图表。 |
| **[!UICONTROL 图例可见]** | 显示图例文字。 |
| **[!UICONTROL 限制最大项目数]** | 限制可视化图表显示的项目数。选择后，定义最大项目数。 |
| **[!UICONTROL 显示注释]** | 显示对此可视化图表所做的注释。 |
| **[!UICONTROL 隐藏标题]** | 隐藏可视化图表的标题。 |
| **[!UICONTROL 将 Y 轴固定在 0]** | 强制将 Y 轴底部设为零。如果图表上绘制的所有值都远远大于零，则图表默认会将 Y 轴底部设为非零值。如果启用此选项，则 Y 轴将被强制设为零（并重新绘制图表）。 |
| **[!UICONTROL 显示双轴]** | 显示两个不同量度的左 Y 轴和右 Y 轴。此选项仅适用于有两个量度的情况。在所绘制量度的数量级大小不同时，双轴非常有用。 |
| **[!UICONTROL 显示 X 轴]** | 在可视化图表中显示 X 轴。 |
| **[!UICONTROL 显示 Y 轴]** | 在可视化图表中显示 Y 轴。 |
| **[!UICONTROL 在线形图中显示条形铃]** | 在组合图可视化图表的线形图可视化图表中显示条形铃。 |
| **[!UICONTROL 标准化]** | 强制所有量度按等比例计算。在所绘制量度的数量级大小不同时，等比例非常有用。 |
| **[!UICONTROL 显示异常情况]** | 通过显示异常检测来增强线形图和自由格式表。线形可视化图表中的异常检测包括预期值（虚线）和预期范围（阴影带）。 |
| **[!UICONTROL 显示预测]** | 通过显示预测值来增强线形图和自由格式表。 |
| **[!UICONTROL 显示最小值]** | 在可视化图表中显示最小值。 |
| **[!UICONTROL 显示最大值]** | 在可视化图表中显示最大值。 |
| **[!UICONTROL 显示趋势线]** | 在可视化图表中显示趋势线。选中后，您可以从下拉菜单中选择趋势线类型。 |

您可以为您创建的所有可视化图表自定义设置。有关更多信息，请参阅[用户偏好设置](/help/analyze/analysis-workspace/user-preferences.md)。


## 上下文菜单 {#right-click}

使用可视化图表标题上的上下文菜单（可通过替代选择获得，例如，使用鼠标右键单击）来访问可视化图表的附加功能。并非所有选项都适用于任何可视化图表。

![通过右键单击选项显示附加可视化图表设置。选项将在下一部分中描述。](assets/right-click.png)

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 插入复制的可视化内容]** | 将复制的可视化图表粘贴（插入）到项目中的其他位置或完全不同的项目中。 |
| **[!UICONTROL 将数据复制到剪贴板]** | [将可视化图表中的数据](/help/analyze/analysis-workspace/curate-share/download-send.md#copy-to-clipboard)复制到剪贴板。 |
| **[!UICONTROL 将选择复制到剪贴板]** | [将可视化图表中的选定内容](/help/analyze/analysis-workspace/curate-share/download-send.md#copy-to-clipboard)复制到剪贴板。 |
| **[!UICONTROL 将项目下载为 CSV（*维度名称*）]** | [将可视化图表的维度项](/help/analyze/analysis-workspace/curate-share/download-send.md#download-items-as-csv)（最多50,000个）下载到您的本地设备。 所选维度最多可有 50,000 个维度项。 |
| **[!UICONTROL 复制可视化图表]** | 复制可视化图表，您可以将其插入到项目中的其他位置或完全不同的项目中。 |
| **[!UICONTROL 下载数据 CSV]** | [将可视化图表显示的数据](/help/analyze/analysis-workspace/curate-share/download-send.md#download-as-csv)下载到您的本地设备。 |
| **[!UICONTROL 复制可视化]** | 生成一个与可视化图表完全相同的副本。 |
| **[!UICONTROL 编辑描述]** | 添加（或编辑）可视化图表的文本描述。请参阅[文本](text.md)。 |
| **[!UICONTROL 获取可视化图表链接]** | 将链接直接复制并共享到可视化图表。共享链接对话框会显示该链接。选择“复制”将链接复制到剪贴板。 |
| **[!UICONTROL 从头开始]** | 删除当前可视化图表的设置，以便您从头开始重新配置。 |


## 配置

某些可视化图表（例如同类群组表、流失、流量等）有配置对话框，可帮助您生成可视化图表。使用可视化图表顶部的![编辑](/help/assets/icons/Edit.svg)来访问和更改配置。

![配置窗格](assets/configuration.png)

## 可视化

如果您不确定选择哪种可视化图表，请在任意自由格式表行（将光标悬停于上方即可显示）中选择 ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg) **[!UICONTROL 可视化]**。这一选择是添加可视化图表最快的方法。Analysis Workspace 针对哪种可视化图表最适合您的数据做出有根据的推测。例如，如果您选择了一行，则会创建趋势[线形图](line.md)。如果您选择了三个过滤器行，则会创建[维恩](venn.md)图。

![快速可视化](assets/quick-viz.png)


<!--
## Settings {#settings}

![](assets/settings.png)

| Setting | Description |
| --- | --- |
| Visualization Type | Change the type of visual used to depict the data. |
| Granularity | For trended visualizations, you can change the time granularity (day, week, month, etc.) from this drop-down list. This change also applies to the data source table. |
| Percentages | Displays values in percentages. |
| 100% Stacked | This setting on area stacked, bar stacked or horizontal bar stacked visualizations turns the chart into a "100% stacked" visualization. Example: ![Stacked 100%](assets/stacked_100_percent.png) |
| Legend Visible | Lets you hide the detailed legend text for the Summary Number/Summary Change visualization. |
| Limit Max Items | Lets you limit the number of items that a visualization displays. |
| Anchor Y Axis at Zero | If all the values plotted on the chart are considerably above zero, the chart default will make the bottom of the y-axis NON-ZERO. If you check this box, the y-axis will be forced to zero (and it will re-draw the chart). |
| Normalization | Forces metrics to equal proportions. This is helpful when plotted metrics are of very different magnitudes. |
| Display Dual Axis | Only applies if you have two metrics - you can have a y-axis on the left (for one metric) and on the right (for the other metric). This is helpful when plotted metrics are of very different magnitudes. |
| Show Anomalies | Enhances line graphs and freeform tables by displaying anomaly detection. Anomaly detection in line visualizations includes an expected value (dashed line) and an expected range (shaded band). |

## Legend {#legend}

A visualization legend helps you to relate date in a source table to plotted series in the visualization. The legend is interactive - you can click a legend item to show/hide a series in the visualization. This is helpful if you want to simplify the data being visualized. 

Additionally, you can rename legend labels to help you make visuals more consumable. Note: legend editing does **not** apply to: Treemap, Bullet, Summary Change/Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

To edit a legend label:

1. Right-click one of the legend labels.
1. Click **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Enter the new label text.
1. Press **[!UICONTROL Enter]** to save.

## Right-click menu {#right-click}

Additional functionality for a visualziation is available by right-clicking on the visualization header. Settings will vary by visualization. Some of the settings available are:

![](assets/right-click.png)

| Setting | Description |
| --- | --- |
| Insert Copied Panel/Visualization|Lets you paste ("insert") a copied panel or visualization to another place within the project, or into a completely different project. |
| Copy Visualization | Lets you right-click and copy a visualization, so that you can insert it to another place within the project, or into a completely different project. |
| [Download items as CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hans&#download-items) | Download up to 50,000 dimension items for the selected dimension as a CSV. |
| [Download data as CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hans&#download-data) | Download visualization data source as a CSV. |
| Duplicate Visualization | Makes an exact duplicate of the current visualization, which you can then modify. |
| Edit Description | Add (or edit) a text description for the visualization. |
| Get Visualization Link | Lets you direct someone to a specific visualization within a project. When the link is clicked, the recipient will be required to login before being directed to the exact visualization linked to. |
| Start Over | (Works for Flow, Venn, Histogram) Deletes the configuration for the current visualization so you can re-configure it from scratch. |

## Create Visual icon {#quick-viz}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row (available on hover). This the the fastest way to add a visualization. Clicking it prompts Analysis Workspace to take an educated guess at which visualization would best fit your data. For example, if you have 1 row selected, it will create a trended line graph. If you have 3 segment rows selected, it will create a Venn diagram. 

![](assets/quick-viz.png)

## Change the scale axis on visualizations

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/41450/?quality=12&captions=chi_hans)

-->
