---
description: 了解如何在Analysis Workspace中将组件添加到项目
title: 使用 Analysis Workspace 中的组件
feature: Workspace Basics
role: User, Admin
exl-id: fb56e794-67e3-4f85-960e-b90684300fa0
source-git-commit: 9fcebd7a8fb3a3d98eebef53a748c8ac585cbcd1
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 16%

---

# 使用 Analysis Workspace 中的组件

组件构成了Analysis Workspace中任何项目的实际数据。 组件由维度、量度、区段和日期范围组成。 您可以将组件拖到可视化图表或面板中，以将其添加到项目中。

有关可添加组件类型的概述信息，请参阅[组件概述](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。

>[!TIP]
>
>有关每个组件的信息，请在Analysis Workspace的左边栏中选择组件名称旁边的信息图标，或参阅[Analytics组件指南](/help/components/home.md)。

## 开始将组件添加到项目

1. [在Analysis Workspace中创建项目](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)（如果尚未创建）。

1. [添加面板](/help/analyze/analysis-workspace/c-panels/panels.md)或[将可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)添加到Analysis Workspace中的项目。

   如果将组件添加到空白项目，则会自动创建自由格式表可视化图表。

1. 选择左边栏中的&#x200B;**[!UICONTROL 组件]**&#x200B;图标。

   ![](assets/build-components.png)

1. 滚动到或搜索要添加的组件，然后将其拖到项目内的面板或可视化中。

1. （可选）将组件拖动到面板标题中的区段放置区域。

   区段适用于面板中的所有内容。

   有关如何使用面板上的区段放置区域来筛选面板的信息，请参阅[面板概述](/help/analyze/analysis-workspace/c-panels/panels.md)中的[放置区域](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone)。

   ![将片段放入拖放区](assets/segment-dropzone.png)

1. 有关更多详细信息，请根据要添加的组件类型，继续执行以下部分之一：

   * [将维度添加到项目](#add-dimensions-to-a-project)

   * [将量度添加到项目](#add-metrics-to-a-project)

   * [将区段添加到项目](#add-segments-to-a-project)

   * [向项目添加日期范围](#add-date-ranges-to-a-project)

## 将维度添加到项目

[Dimension](/help/components/dimensions/overview.md)是Adobe Analytics中通常包含字符串值的变量。 常见维度包括[页面](/help/components/dimensions/page.md)、[反向链接域](/help/components/dimensions/referring-domain.md)或 [eVar](/help/components/dimensions/evar.md)。相反，[量度](/help/components/metrics/overview.md)包含与维度相关的数字值。基本报告根据数值列（量度）显示字符串值的行（维度）。

1. 开始向Analysis Workspace中的项目添加维度，如[开始向项目添加组件](#begin-adding-components-to-a-project)中所述。

1. 选择以下方法之一来添加维度，并确定要分析的数据类型：

   * 将维度拖动到Analysis Workspace中的可视化图表（例如自由格式表）。

     ![将维度添加到项目](assets/add-dimensions.png)

   * 将一个或多个维度从左边栏拖到区段拖放区域以创建临时区段，如[将区段添加到项目](#add-segments-to-a-project)中所述。

     ![将片段放入拖放区](assets/segment-dropzone.png)

1. （可选）您可以在Analysis Workspace中通过其他组件划分维度和维度项。

   有关详细信息，请参阅[划分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。

有关如何在Analysis Workspace中使用维度的详细信息，请参阅[预览维度](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md)、[划分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)和[时间划分维度](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md)。

## 将量度添加到项目

[指标](/help/analyze/analysis-workspace/components/apply-create-metrics.md)允许您量化Analysis Workspace中的数据点。 它们最常用作可视化中的列，并与维度相关联。

要在Analysis Workspace中将指标添加到项目，请执行以下操作：

1. 开始向Analysis Workspace中的项目添加量度，如[开始向项目添加组件](#begin-adding-components-to-a-project)中所述。

1. 选择以下方法之一以在Analysis Workspace中添加量度：

   * 将量度拖动到空的自由格式表中的量度放置区，可查看在项目的日期期间内的量度趋势。

     ![将量度添加到项目](assets/add-metrics.png)

   * 存在维度时拖动一个指标，以查看该指标与每个维度项的比较。

   * 将一个指标拖到现有指标标题的顶部即可替换它。

   * 将一个指标拖到标题旁边可以并排查看两个指标。

有关如何在Analysis Workspace中使用指标的详细信息，请参阅[指标](/help/analyze/analysis-workspace/components/apply-create-metrics.md)。

## 将区段添加到项目

[区段](/help/components/segmentation/seg-overview.md)允许您根据特性或特定交互来识别访客的子集。

您可以通过以下任意方式在Analysis Workspace中使用区段：

### 将区段添加到面板

将区段添加到面板时，区段将应用于面板中的所有内容。

有关如何使用面板上的区段放置区域来筛选面板的信息，请参阅[面板概述](/help/analyze/analysis-workspace/c-panels/panels.md)中的[放置区域](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone)。

### 向自由格式表中的列添加区段

向自由格式表中的列添加区段时，区段会应用于表列中的所有内容。

### 创建计算量度时使用区段

在计算指标生成器中，可在指标定义中应用区段。

有关详细信息，请参阅[分段量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md)。

## 向项目添加日期范围

[日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md)决定Analysis Workspace中的报表时间范围，并可应用于项目中的一个或多个面板。

默认情况下，每个面板都包含日期范围。 有多种方法可以更新面板的日期范围。 在Analysis Workspace中更新面板日期范围的一种方法是从左边栏拖动日期范围组件：

1. 开始向Analysis Workspace中的项目添加日期范围，如[开始向项目添加组件](#begin-adding-components-to-a-project)中所述。

1. 将日期范围从左边栏拖到面板右上方的当前日期范围内。

   ![删除日期范围](assets/daterange-drop.png)

有关如何在Analysis Workspace中使用日历和日期范围的更多信息，请参阅[日历和日期范围概述](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)。
