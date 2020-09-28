---
description: 面板是表和可视化的集合
title: 面板概述
translation-type: tm+mt
source-git-commit: f772494e6e3f8b5ab186c5b0c891f4f5043470f9
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 15%

---


# 面板概述

A [!UICONTROL panel] is a collection of tables and visualizations. 您可以通过工作区左上角的图标访问面板。当您希望根据时段、报表包或分析用例组织项目时，面板会很有帮助。 Analysis Workspace提供以下面板类型：

| 面板名称 | 描述 |
|---|---|
| [空白面板](blank-panel.md) | 从可用的面板和可视化中进行选择，以开始分析。 |
| [快速分析面板](quickinsight.md) | 快速构建自由格式表和随附的可视化图表，以便更快地分析和发现见解。 |
| [“Analytics for Target”面板](a4t-panel.md) | 在 Analysis Workspace 中分析 Target 的活动和体验。 |
| [归因面板](attribution.md) | 可使用任何维度和转化量度，采用可视化图表的方式，快速比较任意数量的归因模型。 |
| [自由格式面板](freeform-panel.md) | 执行无限制的比较和细分，然后添加可视化以讲述丰富的数据故事。 |
| [“媒体并发查看器”面板](media-concurrent-viewers.md) | 分析一段时间内的并发查看者，了解有关并发峰值的详细信息，并且可以进行细分和比较。 |
| [区段比较面板](c-segment-comparison/segment-comparison.md) | 快速比较所有数据点中的两个细分，自动找到相关差异。 |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights]、Blank [!UICONTROL 和Freeform] 面板是开始分析的绝佳场所，而Analytics for [!UICONTROL 目标、Analytics for] Attribution IQ、Aligns Viewers和Carposion可以更高级的分析方式自行进行。 项目中有一个 `"+"` 按钮，通过该按钮，您可以随时添加空白面板。

The default starting panel is the [!UICONTROL Freeform] panel, but you can make the [blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) your default as well.

## 面板报告套件 {#report-suite}

面板中的表和可视化从面板右 [!UICONTROL 上方选] 定的报表包中导出数据。 报表包还确定左边栏中可用的组件。 在项目中，您可以使用一个或 [多个报表包](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) ，具体取决于分析用例。

![](assets/panel-report-suite.png)

## 面板日历 {#calendar}

面板日历控制面板中表格和可视化的报告范围。

注意：如果在表、可视化或面板拖放区中使用（紫色）日期范围组件，它将覆盖面板日历。

![](assets/panel-calendar.png)

## 面板拖放区 {#dropzone}

面板拖放区允许您将区段和下拉过滤器应用于面板中的所有表和可视化。 您可以对面板应用一个或多个过滤器。 可通过单击编辑铅笔来修改每个滤镜上方的标题，也可以右键单击以完全删除它。

### 细分过滤器

将左边栏中的任意段拖放到面板拖放区，开始筛选面板。

![](assets/segment-filter.png)

### 临时细分过滤器

非区段组件也可直接拖入拖放区以创 **建临时区段**，节省了转至区段生成器的时间和精力。 以这种方式创建的区段会自动定义为点击级别区段。 可以通过单击段旁的信息图标(i)，然后单击铅笔形编辑图标并在段生成器中编辑来修改此定义。

临时区段是项目的本地区段，除非公开，否则不会显示在左边栏中。

![](assets/adhoc-segment-filter.png)

### 下拉过滤器 {#dropdown-filter}

除细分过滤器外，下 **拉过滤器还使** 您能够以受控方式与数据交互。 例如，您可以为移动设备类型添加下拉筛选器，以便按平板电脑、手机或桌面对面板进行分段。

下拉式过滤器还可用于将多个项目合并到一个项目中。 例如，如果应用了不同国家／地区段的同一项目的多个版本，您可以将所有版本合并到单个项目中并添加国家／地区下拉列表筛选器。

![](assets/dropdown-filter-intro.png)

**创建和使用下拉过滤器:**

![](assets/create-dropdown.png)

1. 要使用Dimension项创建下拉 [!UICONTROL 筛选器](如营销 [!UICONTROL 渠道维中的值] )，请单击左边栏中维旁边的右箭头图标。 这将显示所有可用项。 从左边栏中选择一个或多个组件项，并在按住Shift键的同时将 **它们拖放到面板拖放区**。 这会将组件转换为下拉筛选器，而不是单个区段。
1. 要使用度量、段或日期范围等其他组件创建下拉筛选器，请从左边栏中的一个组件类型中进行选择，并在按住Shift键的同 **时放入面板拖放区**。
1. 从下拉列表中选择一个选项以更改面板中的数据。 You can also choose to not filter any of the panel data by selecting **[!UICONTROL No filter]**.

[观看视频](https://www.youtube.com/watch?v=vpJywtsFVPI) ，进一步了解如何向项目添加下拉过滤器。
