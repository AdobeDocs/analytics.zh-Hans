---
description: 了解如何在Analysis Workspace中将组件添加到项目
title: 在Analysis Workspace中使用组件
feature: Workspace Basics
role: User, Admin
source-git-commit: 0928628c9cffa91f90fa5d8af535eb834bb7502d
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 15%

---

# 在Analysis Workspace中使用组件

组件构成了Analysis Workspace中任何项目的实际数据。 组件由维度、量度、区段和日期范围组成。 您可以将组件拖到可视化图表或面板中，以将其添加到项目中。

有关可添加组件类型的概述信息，请参见 [组件概述](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

>[!TIP]
>
>有关每个组件的信息，请在Analysis Workspace的左边栏中选择组件名称旁边的信息图标，或参阅 [Analytics组件指南](/help/components/home.md).

## 开始将组件添加到项目

1. [在Analysis Workspace中创建项目](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) 如果你还没有的话。

1. [添加面板](/help/analyze/analysis-workspace/c-panels/panels.md) 或 [添加可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) 到Analysis Workspace中的项目。

   如果将组件添加到空白项目，则会自动创建自由格式表可视化图表。

1. 选择左边栏中的&#x200B;**[!UICONTROL 组件]**&#x200B;图标。

   ![](assets/build-components.png)

1. 滚动到或搜索要添加组件，然后将其拖动到项目中的面板或可视化图表。

   例如，您可以将区段拖到面板标题中的区段放置区域。

   ![将区段放入放置区域](assets/segment-dropzone.png)

1. 有关更多详细信息，请根据要添加的组件类型，继续执行以下部分之一：

   * [将维度添加到项目](#add-dimensions-to-a-project)

   * [将量度添加到项目](#add-metrics-to-a-project)

   * [将区段添加到项目](#add-segments-to-a-project)

   * [向项目添加日期范围](#add-date-ranges-to-a-project)

## 将维度添加到项目

[Dimension](/help/components/dimensions/overview.md) 是Adobe Analytics中通常包含字符串值的变量。 常见维度包括[页面](/help/components/dimensions/page.md)、[反向链接域](/help/components/dimensions/referring-domain.md)或 [eVar](/help/components/dimensions/evar.md)。相反，[量度](/help/components/metrics/overview.md)包含与维度相关的数字值。基本报告根据数值列（量度）显示字符串值的行（维度）。

1. 在Analysis Workspace中开始向项目添加维度，如中所述 [开始将组件添加到项目](#begin-adding-components-to-a-project).

1. 选择以下方法之一来添加维度，并确定要分析的数据类型：

   * 将维度拖动到Analysis Workspace中的可视化图表（例如自由格式表）。

     ![将维度添加到项目](assets/add-dimensions.png)

   * 将一个或多个维度从左边栏拖至区段拖放区域以创建临时区段，如中所述 [将区段添加到项目](#add-segments-to-a-project).

     ![将区段放入放置区域](assets/segment-dropzone.png)

有关如何在Analysis Workspace中使用维度的更多信息，请参阅 [预览维度](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md)， [划分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)、和 [时间划分维度](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md).

## 将量度添加到项目

[量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md) 允许您量化Analysis Workspace中的数据点。 它们最常用作可视化中的列，并与维度相关联。

要在Analysis Workspace中将指标添加到项目，请执行以下操作：

1. 开始在Analysis Workspace中将指标添加到您的项目，如中所述 [开始将组件添加到项目](#begin-adding-components-to-a-project).

1. 选择以下方法之一以在Analysis Workspace中添加量度：

   * 将量度拖动到空的自由格式表中的量度放置区，可查看在项目的日期期间内的量度趋势。

     ![将量度添加到项目](assets/add-metrics.png)

   * 存在维度时拖动一个指标，以查看该指标与每个维度项的比较。

   * 将一个指标拖到现有指标标题的顶部即可替换它。

   * 将一个指标拖到标题旁边可以并排查看两个指标。

有关如何在Analysis Workspace中使用量度的更多信息，请参阅 [量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

## 将区段添加到项目

[区段](/help/components/segmentation/seg-overview.md) 允许您根据特性或特定交互来识别访客的子集。

要在Analysis Workspace中将区段添加到项目，请执行以下操作：

1. 在Analysis Workspace中开始向项目添加区段，如中所述 [开始将组件添加到项目](#begin-adding-components-to-a-project).

1. 选择下列方法之一以开始筛选面板：

   * 将单个区段从左边栏拖至区段拖放区域。

     ![将区段放入放置区域](assets/segment-dropzone.png)

   * 按住Shift或Ctrl键在左边栏中选择多个区段，然后按住Shift键，将多个区段拖放到区段拖放区域。

     ![将多个区段放入放置区域](assets/segment-dropzoone-multiple.png)

     这将创建一个下拉菜单，通过该菜单，面板的用户可以选择要应用的过滤器。 下拉菜单包含 [!UICONTROL **无筛选器**] 用户可以选择的选项，这将使面板保持未过滤状态。

     您可以从下拉菜单中选择(x)以删除任何选项。 如果您删除 [!UICONTROL **无筛选器**] 选项，则需要过滤器。

   * 通过将非区段组件拖放到拖放区域来创建临时区段。 这可以节省转到区段生成器的时间和精力。 通过这种方式创建的区段自动定义为点击级别区段。通过单击区段旁的信息图标 (i)、单击铅笔形状编辑图标并在区段生成器中进行编辑，可以修改此定义。

     临时区段是一种快速区段，在项目本地。 除非您将其公开，否则它们不会出现在左侧栏中。

     有关更多信息，请参阅[快速区段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)。

有关如何使用面板上的区段拖放区域来筛选面板的更多信息，请参阅 [放置区域](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) 在 [面板概述](/help/analyze/analysis-workspace/c-panels/panels.md).

## 向项目添加日期范围

[日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) 确定Analysis Workspace中的报表时间范围，并可应用于项目中的一个或多个面板。

默认情况下，每个面板都包含日期范围。 有多种方法可以更新面板的日期范围。 在Analysis Workspace中更新面板日期范围的一种方法是从左边栏拖动日期范围组件：

1. 开始在Analysis Workspace中为项目添加日期范围，如中所述 [开始将组件添加到项目](#begin-adding-components-to-a-project).

1. 将日期范围从左边栏拖到面板右上方的当前日期范围内。

   ![放置日期范围](assets/daterange-drop.png)

有关如何在Analysis Workspace中使用日历和日期范围的更多信息，请参阅 [日历和日期范围概述](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).
