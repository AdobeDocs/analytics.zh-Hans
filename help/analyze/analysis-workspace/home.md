---
keywords: Analysis Workspace
title: Analysis Workspace 概述
topic: Reports and analytics
uuid: 4df6be48-2c88-4b9d-9536-ed64ffbb6ee4
translation-type: tm+mt
source-git-commit: efbbf94882a406e95791e38e80f86691285986a6

---


# Analysis Workspace 概述

Analysis Workspace 去除了单一 Analytics 报表存在的所有典型限制。它提供了一个功能强大而灵活的画布，用于构建自定义分析项目。您可以向一个项目拖放任意数量的数据表、可视化信息和组件（维度、量度、区段和时间粒度）。可以即时创建划分和区段、创建用于分析的同类群组、创建警报、比较区段、进行流量和流失分析，并且组织和计划报表以与公司的其他人员共享。

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

## 概述视频

>[!VIDEO](https://video.tv.adobe.com/v/26266?quality=12)

完整的 YouTube 播放列表可在[此处](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)获得。

>[!NOTE]
>
> 请参阅 [Analysis Workspace 中的新增功能](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)以获取相关功能更新。

## 实现项目元素和组件的全面控制

Analysis Workspace 可以提供自由和灵活性。

* 可拖放组件（维度、量度、区段和时间粒度）
* 可在项目中拖放多种可视化信息
* 根据需要，可随时在项目中移动、堆叠可视化信息并调整其大小

![](assets/fa_project_new.png)

请参阅[创建一个 Analysis Workspace 项目](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)，以了解更多信息。

## 在一个项目中显示多种可视化信息

您可以根据需要，在项目中拖放多种可视化信息。

![](assets/visualizations-multiple.png)

创建一个显示变化（百分比）的项目，并在其中包含与自由格式数据表中单元格对应的多项可视化信息。

![](assets/visualizations-multiple02.png)

请参阅[创建一个 Analysis Workspace 项目](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)，以了解更多信息。

## 内部链接到面板和可视化

要与 Analysis Workspace 的[富文本编辑](/help/analyze/analysis-workspace/visualizations/text.md)功能一起使用，您可以从文本框向下链接到项目中的特定面板和可视化图表，如创建项目目录。您可以像共享项目链接一样共享这些链接，以将某个人定向到项目中的特定可视化或面板。新增了名为“获取面板链接”和“获取可视化图表链接”的右键单击选项。要将内部链接添加到您的项目，请执行以下操作：

1. 将文本可视化拖到项目中可能需要某些上下文的可视化或表格旁边。
1. 使用相关内容（例如目录）填充文本框，然后突出显示要链接到面板或可视化的项目，例如“成功量度”。

   ![](assets/intra-linking1.png)

1. 滚动到该面板或可视化，并右键单击面板的标题。
1. 向下滚动并选择 **[!UICONTROL Get Panel Link]** 或 **[!UICONTROL Get Visualization Link]**:

   ![](assets/intra-linking2.png)

1. 复制该链接，并将其添加到文本可视化中的“成功量度”超链接。单击复选标记以保存文本。

如果您在项目中折叠了面板或可视化，则单击链接将可展开该面板/可视化信息，以便用户可以看到它。

>[!NOTE] 您还可以在右键单击选项 **[!UICONTROL Edit Description]** 中使用此功能。

## 链接到其他项目

You can link users to other projects that may be of interest to them by going to  **[!UICONTROL Share]** > **[!UICONTROL Get Project Link]** and embedding this link in project descriptions, for example.

## 查看选定单元格的动态可视化信息

可选择若干单元格，查看这些单元格可视化信息的动态变化情况。可同步并锁定选定单元格的可视化信息。

![](assets/visualize-selected-cells.png)

## 锁定选定项目或位置

通过锁定可视化信息可以控制与其对应的自由格式数据表来源。

![](assets/manage-data-source.png)

请参阅[管理数据源](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)。

## 呈现选定单元格的趋势可视化信息

创建选定单元格的可视化信息。(右键单击> **[!UICONTROL Trend Selection]**.)

![](assets/trend-selection.png)

趋势选择现已&#x200B;**关联**&#x200B;到下面的表，因此，如果选择表中的不同行，趋势图将反映出该行的内容。

![](assets/trend-selection2.png)

## 维度和维度项目划分

作为零售商，您能够采取比以往更加深入的方式来调研促销活动，了解怎样可以更好地吸引客户。您可以采用任何方式，无限制地划分数据以满足自己的特定需求；使用相关的量度、维度、区段、时间线以及其他分析划分值来构建查询。

![步骤结果](assets/fa_data_table_actions.png)

请参阅[划分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。

## 根据表的选定内容创建区段

选择自由格式表中的单元格，然后根据选定的内容创建区段。

多个区段之间可进行比较，而且可以立即创建并应用区段。您可以应用多个区段，根据行为和交互情况来重点关注特定的客户，然后进行比较和对照。

![](assets/segment_inline.png)

如果按照项目级别将区段放在自由格式面板中，该区段则会应用在整个项目中。

![](assets/segment-panel.png)

请参阅 [区段](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md)。

## 在项目和组件中应用标记

可将标记应用到 Analysis Workspace 的项目和组件中：

* 在“信息”面板中可应用或创建项目级别的标记 (![](assets/information_icon.png))。

* 从“组件”面板中右键单击组件，可应用（或创建）标记。
* 在搜索栏中使用“#”可查找标记。

## 组件操作

从位于组件左边栏顶部的“操作”菜单执行组件级别的操作。Select a component and click **[!UICONTROL Actions]** to view the actions.

| 组件操作 | 描述 |
|--- |--- |
| 标记 | 通过对组件应用标记来组织或管理组件。然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目” |
| 收藏 | 将组件添加到您的收藏夹列表中。然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目”。 |
| 批准 | 批准组件以使其成为规范。然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目” |
| 共享 | 仅适用于区段。 |
| 删除 | 仅适用于区段。 |

请参阅[可视化](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)，以了解更多信息。

## 关于其他功能的描述

**拖动和堆叠项**

组件

* 维度
* 区段
* 量度
* 日期范围
* 时间粒度（小时、天、周等等）。

**多个自由格式表和多项可视化信息**

从技术角度来讲，可以向面板添加的自由格式表和可视化信息的数量并无限制。此外，您可以针对每个自由格式表或自由格式表的选定行，运行新的可视化（或将其导出为 CSV 格式）。

**分类、排序和复制列**

* 排序日期范围预设（不包括自定义日期范围）。
* 按住 Ctrl（或 Command），单击并拖动可复制该列，拖动复制的列会将其粘贴至表中的新位置。

请参阅 [Analysis Workspace 中可用的热键](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)，以获取更多信息。

**选择并操作**

您可以像在 Excel 中选择行和列那样来进行选择。然后，您可以在选定的内容上执行操作。例如：

* 通过选定的内容创建可视化信息
* 复制到剪贴板（Ctrl 或 Command + C）
* 划分多个选定的行。选择若干行，然后将某个维度拖放到选定的行上。或者，右键单击选定的行，然后使用“划分”菜单。

**自动保存和未保存的更改**

当您尝试关闭浏览器（或使用“返回”按钮）并且尚未保存项目时，系统会提示您保存对项目所做的更改。如果系统崩溃，那么在您加载项目时，会收到一个将该项目还原至以前状态的警报。

现有（非新）项目只有在浏览器崩溃时，或在其他一些没有机会保存的情况下才会自动保存。

**所有访问**

Analysis Workspace 特有的默认区段。*`All Visits`* 显示您添加到数据表中的组件的所有访问次数。

**计算量度**

使用的计算方法与使用标准量度相同。

请参阅[计算量度](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/cm-overview.html)。
