---
keywords: Analysis Workspace
title: Analysis Workspace 概述
topic: Reports and analytics
uuid: 4df6be48-2c88-4b9d-9536-ed64ffbb6ee4
translation-type: tm+mt
source-git-commit: 5161ccaf333908525c261b73419899918554b91c

---


# Analysis Workspace 概述

分析工作区消除了单个Analytics报表的所有典型限制。 它为构建自定义分析项目提供了强大、灵活的画布。 将任意数量的数据表、可视化和组件（维度、度量、区段和时间粒度）拖放到项目中。 即时创建细分和细分，创建分析群，创建警报，比较细分，进行流量和流失分析，以及管理和计划报告，以便与业务中的任何人共享。

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

## 概述视频

>[!VIDEO](https://video.tv.adobe.com/v/26266?quality=12)

完整的 YouTube 播放列表可在[此处](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)获得。

>[!NOTE]
>
> 请参阅 [Analysis Workspace 中的新增功能](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)以获取相关功能更新。

## 实现项目元素和组件的全面控制

分析工作区提供了自由和灵活性：

* 拖放组件（维度、指标、细分和时间粒度）
* 将多个可视化拖放到项目中
* 在项目中随时随地移动、调整大小和堆叠可视化

![](assets/fa_project_new.png)

请参阅[创建一个 Analysis Workspace 项目](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)，以了解更多信息。

## 在一个项目中显示多种可视化信息

您可以根据需要，在项目中拖放多种可视化信息。

![](assets/visualizations-multiple.png)

创建一个显示更改百分比的项目，其中包含对应于自由格式数据表中单元格的多个可视化。

![](assets/visualizations-multiple02.png)

请参阅[创建一个 Analysis Workspace 项目](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)，以了解更多信息。

## 内部链接到面板和可视化

要与 Analysis Workspace 的[富文本编辑](/help/analyze/analysis-workspace/visualizations/text.md)功能一起使用，您可以从文本框向下链接到项目中的特定面板和可视化图表，如创建项目目录。您可以像共享项目链接一样共享这些链接，以将某个人定向到项目中的特定可视化或面板。新增了名为“获取面板链接”和“获取可视化图表链接”的右键单击选项。要向项目添加内部链接，请执行以下操作：

1. 将文本可视化拖到项目中，可能在需要某些上下文的可视化或表旁边。
1. 在文本框中填充内容表，然后突出显示要链接到面板或可视化的项目，如“成功量度”。

   ![](assets/intra-linking1.png)

1. 滚动到该面板或可视化，并右键单击该面板的标题。
1. 向下滚动并选择 **[!UICONTROL Get Panel Link]** 或 **[!UICONTROL Get Visualization Link]**:

   ![](assets/intra-linking2.png)

1. 复制该链接并将其添加到文本可视化中的“成功量度”超链接。 单击复选标记以保存文本。

如果项目中折叠了面板或可视化，则单击链接将展开面板／可视化，以便用户能够看到它。

>[!NOTE] 您还可以在右键单击选项中 **[!UICONTROL Edit Description]** 使用此功能。

## 链接到其他项目

You can link users to other projects that may be of interest to them by going to  **[!UICONTROL Share]** > **[!UICONTROL Get Project Link]** and embedding this link in project descriptions, for example.

## 查看选定单元格的动态可视化信息

选择单个单元格并查看可视化动态更改。 [将可视化与选定单元格同步](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_9D66A001586F49CEB0C565581E44957C) ，并将其锁定。

![](assets/visualize-selected-cells.png)

## 锁定选定项目或位置

锁定可视化允许您控制与可视化相对应的自由形式数据表源。

![](assets/manage-data-source.png)

See [Manage data sources](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md).

## 呈现选定单元格的趋势可视化信息

创建选定单元格的可视化信息。(右键单击> **[!UICONTROL Trend Selection]**.)

![](assets/trend-selection.png)

趋势选择现已&#x200B;**关联**&#x200B;到下面的表，因此，如果选择表中的不同行，趋势图将反映出该行的内容。

![](assets/trend-selection2.png)

## 维度和维度项目划分

作为零售商，您可以比以往更深入地了解活动，以了解如何更好地吸引客户。 根据您的特定需求无限细分数据；使用相关指标、维度、细分、时间线和其他查询细分值构建分析。

![步骤结果](assets/fa_data_table_actions.png)

请参阅[划分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。

## 根据表的选定内容创建区段

在自由格式表中选择单元格，然后从选择中创建区段。

比较多个细分，即时创建并应用细分。 您可以应用多个细分，根据行为和互动关注特定客户，然后进行比较和对比。

![](assets/segment_inline.png)

将区段拖放到项目级别的自由形式面板，该区段将应用于整个项目。

![](assets/segment-panel.png)

请参阅 [区段](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md)。

## 在项目和组件中应用标记

可将标记应用到 Analysis Workspace 的项目和组件中：

* 在“信息”面板中可应用或创建项目级别的标记 (![](assets/information_icon.png))。

* 在“组件”面板中右键单击组件以标记（或创建标记）。
* 在“搜索”字段中使用#查找标记。

## 组件操作

从位于组件左边栏顶部的“操作”菜单执行组件级别的操作。Select a component and click **[!UICONTROL Actions]** to view the actions.

| 组件操作 | 描述 |
|--- |--- |
| 标记 | 通过对组件应用标记来组织或管理组件。然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目” |
| 收藏 | 将组件添加到收藏夹列表。 然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目”。 |
| 批准 | 批准组件以使其成为规范。 然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目” |
| 共享 | 仅适用于区段。 |
| 删除 | 仅适用于区段。 |

See [Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) for more information.

## 关于其他功能的描述

**拖动和堆叠项**

组件

* 维度
* 区段
* 量度
* 日期范围
* 时间间隔（小时、天、周等）。

**多个自由格式表和多项可视化信息**

对于可添加到面板的自由格式表和可视化的数量没有技术限制。 此外，您还可以运行新的可视化（或导出到CSV），每个自由格式表或表的选定行。

**分类、排序和复制列**

* 排序日期范围预设（不包括自定义日期范围）。
* CTRL（或Command）+单击+拖动列可复制列，当您拖动该列时，它将粘贴到表中的新位置。

请参阅 [Analysis Workspace 中可用的热键](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)，以获取更多信息。

**选择并操作**

您可以选择行和列，其方式与在Excel中选择行和列的方式类似。 然后，您可以对这些选择执行操作。 例如：

* 根据选择创建可视化
* 复制到剪贴板（CTRL或Command + C）
* 划分多行。 选择行，然后将维拖动到选区上。 或者，右键单击选择，然后使用“划分”菜单。

**自动保存和未保存的更改**

如果您尝试关闭浏览器（或使用“返回”按钮），但项目尚未保存，系统会提示您保存更改。 如果系统崩溃，您将在加载项目时收到一条警报以恢复到之前的项目状态。

仅当浏览器崩溃时或在其他情况下没有机会保存现有（非新）项目时，才会自动保存它们。

**所有访问**

Analysis Workspace 特有的默认区段。*`All Visits`* 显示您添加到数据表中的组件的所有访问次数。

**计算量度**

使用计算的方式与使用标准度量的方式相同。

请参阅 [计算量度](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/cm-overview.html)。
