---
title: Analysis Workspace 概述
description: 了解 Analysis Workspace —— Adobe Analytics 的高级分析工具。通过项目、面板、表格、可视化图表及其他组件，使数据生动呈现，并进行内容管理与分析共享。
feature: Workspace Basics
role: User, Admin
exl-id: de95551d-09ea-4461-9bb4-b4ef235e9cd2
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 100%

---

# Analysis Workspace 概述 {#analysis-workspace-overview}

利用 Analysis Workspace，可以快速生成分析以收集洞察，然后与其他人共享这些洞察。可以使用拖放浏览器界面进行分析、添加可视化内容以便直观地呈现数据、梳理数据集以及与您选定的任何人员共享和安排[项目](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)。

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 概述](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]

## 界面

下面的图像和附表解释了 Analysis Workspace 用户界面中的主要元素：

![Analysis Workspace 窗口突出显示了界面的各个部分](assets/analysis-workspace-overview.png)

| 位置 | 名称和功能 |
|:---------:|----------|
| A | 包含项目名称、用于访问功能的菜单结构、返回项目列表的按钮![“返回”按钮](/help/assets/icons/ChevronLeft.svg)，以及[分享 Workspace 项目](/help/analyze/analysis-workspace/curate-share/share-projects.md)的&#x200B;**[!UICONTROL 分享]**&#x200B;按钮。<br/>随时选择您的项目名称（例如：新项目）即可更改名称。<br/>选择![取消收藏](/help/assets/icons/StarOutline.svg)将您的项目标记为收藏的项目![收藏](/help/assets/icons/Star.svg)。 |
| B | **按钮面板：**&#x200B;包含用于访问 Analysis Workspace 的主要[功能](#features)的按钮：<ul><li>![WebPage](/help/assets/icons/WebPage.svg) [[!UICONTROL 面板]](/help/analyze/analysis-workspace/c-panels/panels.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL 可视化]](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![策划](/help/assets/icons/Curate.svg)[[!UICONTROL 组件]](/help/components/home.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL 目录]](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![书签](/help/assets/icons/Bookmark.svg) [[!UICONTROL 数据字典]](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **左侧面板：**&#x200B;该区域包含单独的面板、可视化内容、组件或列表。相关内容取决于按钮面板中选择的按钮。 |
| D | **画布：**&#x200B;从左侧面板拖动内容以构建项目的主要区域。当您添加面板、向面板添加可视化效果以及向可视化效果添加组件时，项目会动态更新。您可以创建多个面板，并且在每个面板内可以创建多个可视化效果。<br/>每个面板都基于所选的报表包。所选的报表包决定了可用的组件，例如量度和维度。有关详细信息，请参阅[面板 - 报表包](/help/analyze/analysis-workspace/c-panels/panels.md#report-suite)。 |

## 功能

Analysis Workspace 的主要功能可通过按钮面板使用：

| 图标 | 功能 | 描述 |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL 面板]** | [面板](/help/analyze/analysis-workspace/c-panels/panels.md)可以包含许多表格和可视化内容，用于在项目中对分析进行组织和整理。Analysis Workspace 中提供的许多面板都可以基于一些用户输入来生成整套分析。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL 可视化内容]** | [可视化内容](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)（例如条形图或折线图）可用于直观地呈现数据。在最左侧面板中，选择中间的&#x200B;**[!UICONTROL 可视化内容]**&#x200B;图标可查看所有可用的可视化内容。 |
| ![Curate](/help/assets/icons/Curate.svg) | **[!UICONTROL 组件]** | [组件](/help/components/home.md)包括以下元素：<ul><li>![Dimensions](/help/assets/icons/Dimensions.svg) [维度](/help/components/dimensions/overview.md)</li><li>![Event](/help/assets/icons/Event.svg) [量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md)</li><li>![分段](/help/assets/icons/Segmentation.svg) [区段](/help/components/segmentation/seg-overview.md)</li><li>![Calendar](/help/assets/icons/Calendar.svg) [日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL 目录]** | [目录](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)会将项目中包含的所有面板和可视化内容组织成一个可折叠列表，以便您能够快速访问特定的面板或可视化内容。 |
| ![Bookmark](/help/assets/icons/Bookmark.svg) | **数据字典**  | [数据字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)可以帮助用户和管理员跟踪并更好地理解 Analytics 环境中的组件。 |


## 菜单

Analysis Workspace 的大部分功能可通过拖放以及面板、可视化内容和组件内的上下文菜单实现。

还可以通过 Workspace 菜单和快捷方式或热键使用相关功能。快捷键根据浏览器所运行的操作系统而有所不同。概述见下表。

请注意，您的键盘上可能会使用以下符号：

- **⇧** 表示 **[!UICONTROL *shift *]**键。
- **⌘** 表示 **[!UICONTROL *cmd *]**（命令）。
- **⌃** 表示 **[!UICONTROL *ctrl *]**（控制）。
- **⌥** 表示 **[!UICONTROL *opt *]**（选项）。
- **⎇** 表示 **[!UICONTROL *alt *]**（备选）。

请参阅下表以了解可用菜单的概述。

| **[!UICONTROL 项目]** | Mac 快捷方式 | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 创建项目]** | **[!UICONTROL *Shift+cmd+p *]** | **[!UICONTROL *shift+ctrl+p *]** | 创建一个新项目。 |
| **[!UICONTROL 创建移动记分卡]** | | | [创建新的移动记分卡](/help/analyze/mobile-app/create-scorecard.md)。 |
| **[!UICONTROL 打开……]** | **[!UICONTROL *cmd+o *]** | **[!UICONTROL *ctrl+o *]** | [打开现有项目](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-another-project)。 |
| **[!UICONTROL 打开以前的版本……]** | **[!UICONTROL *opt+cmd+o *]** | **[!UICONTROL *alt+ctrl+o *]** | [打开项目的早期版本](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version)。 |
| **[!UICONTROL 保存]** | **[!UICONTROL *cmd+s *]** | **[!UICONTROL *ctrl+s *]** | [保存项目](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-projects)。 |
| **[!UICONTROL 保存并添加注释……]** | **[!UICONTROL *opt+cmd+s *]** | **[!UICONTROL *alt+ctrl+s *]** | [为您保存的项目版本添加注释](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 另存为……]** | **[!UICONTROL *shift+cmd+s *]** | **[!UICONTROL *shift+ctrl+s *]** | [使用不同的名称和详细信息保存项目](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 刷新项目]** | **[!UICONTROL *opt+r *]** | **[!UICONTROL *alt+r *]** | 刷新项目。 |
| **[!UICONTROL 下载 CSV]** | **[!UICONTROL *shift+cmd+v *]** | **[!UICONTROL *shift+ctrl+v *]** | 将项目下载为 CSV 文件。 |
| **[!UICONTROL 下载 PDF]** | **[!UICONTROL *shift+cmd+b *]** | **[!UICONTROL *shift+ctrl+b *]** | 以 PDF 文档的形式下载项目。 |
| **[!UICONTROL 项目信息和设置]**  | | | 定义项目的设置，例如名称、标记、调色板等。 |
| **[!UICONTROL 用户设置]** | | | [配置使用 Analysis Workspace 的偏好设置](/help/analyze/analysis-workspace/user-preferences.md) 。 |


| **[!UICONTROL 编辑]** | Mac 快捷方式 | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 撤销]** | **[!UICONTROL *cmd+z *]** | **[!UICONTROL *ctrl+z *]** | 撤消上一个操作。 |
| **[!UICONTROL 重做]** | **[!UICONTROL *cmd+shift+z *]** | **[!UICONTROL *ctrl+shift+z *]** | 重新执行上一个操作。 |
| **[!UICONTROL 全部清除]** | **[!UICONTROL *opt+w *]** | **[!UICONTROL *alt+w *]** | 清除当前项目中的所有面板。 |

| **[!UICONTROL 插入]** | Mac 快捷方式 | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 空白面板]** | **[!UICONTROL *opt+b *]** | **[!UICONTROL *alt+b *]** | 插入[空白面板](/help/analyze/analysis-workspace/c-panels/blank-panel.md)。 |
| **[!UICONTROL 媒体并行观众]** | **[!UICONTROL *opt+h *]** | **[!UICONTROL *alt-h *]** | 插入[媒体并行观众](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md)面板。 |
| **[!UICONTROL 媒体播放耗时]** | **[!UICONTROL *opt+i *]** | **[!UICONTROL *alt+i *]** | 插入[媒体播放耗时](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)面板。 |
| **[!UICONTROL 媒体平均分钟观众数]** | **[!UICONTROL *opt+m *]** | **[!UICONTROL *alt+m *]** | 插入[媒体平均分钟观众数](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)面板。 |
| **[!UICONTROL 归因]** | **[!UICONTROL *opt+e *]** | **[!UICONTROL *alt+e *]** | 插入[归因](/help/analyze/analysis-workspace/c-panels/attribution.md)面板。 |
| **[!UICONTROL 自由格式表]** | **[!UICONTROL *opt+a *]** | **[!UICONTROL *alt+a *]** | 插入[自由格式](/help/analyze/analysis-workspace/c-panels/freeform-panel.md)面板。 |
| **[!UICONTROL 快速洞察]** | **[!UICONTROL *opt+j *]** | **[!UICONTROL *alt+j *]** | 插入[快速洞察](/help/analyze/analysis-workspace/c-panels/quickinsight.md)面板。 |
| **[!UICONTROL 自由格式表]** | **[!UICONTROL *opt+1 *]** | **[!UICONTROL *Alt + 1 *]** | 插入[自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)可视化内容。 |
| **[!UICONTROL 折线图]** | **[!UICONTROL *opt+2 *]** | **[!UICONTROL *Alt + 2 *]** | 插入[折线图](/help/analyze/analysis-workspace/visualizations/line.md)可视内容。 |
| **[!UICONTROL 条形图]** | **[!UICONTROL *opt+3 *]** | **[!UICONTROL *Alt + 3 *]** | 插入[条形图](/help/analyze/analysis-workspace/visualizations/bar.md)可视化内容。 |
| **[!UICONTROL 组合]** | **[!UICONTROL *opt+4 *]** | **[!UICONTROL *Alt + 4 *]** | 插入[组合](/help/analyze/analysis-workspace/visualizations/combo-charts.md)可视化内容。 |


| **[!UICONTROL 组件]** | 快捷方式 Mac | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 创建区段……]** | **[!UICONTROL *shift+cmd+e *]** | **[!UICONTROL *shift+ctrl+e *]** | 创建新的[区段](/help/components/segmentation/segmentation-workflow/seg-create.md)。 |
| **[!UICONTROL 创建量度……]** | **[!UICONTROL *shift+cmd+c *]** | **[!UICONTROL *shift+ctrl+c *]** | 创建新的[计算量度](/help/components/calculated-metrics/cm-overview.md)。 |
| **[!UICONTROL 创建日期范围……]** | **[!UICONTROL *shift+cmd+d *]** | **[!UICONTROL *shift+ctrl+d *]** | 创建新的[日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)。 |
| **[!UICONTROL 创建注释……]** | **[!UICONTROL *shift+cmd+o *]** | **[!UICONTROL *shift+ctrl+o *]** | 创建新的[注释](/help/analyze/analysis-workspace/components/annotations/overview.md)。 |
| **[!UICONTROL 刷新组件]** | **[!UICONTROL *opt+shift+r *]** | **[!UICONTROL *alt+shift+r *]** | 刷新项目中的组件。 |

| **[!UICONTROL 共享]** | Mac 快捷方式 | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 与 Workspace 用户共享]** | **[!UICONTROL *cmd+h *]** | **[!UICONTROL *ctrl+h *]** | [与其他 Workspace 用户共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization)。 |
| **[!UICONTROL 与任何人共享]** | **[!UICONTROL *opt+l *]** | **[!UICONTROL *alt+l *]** | [与任何人共享项目的只读版本](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project)。 |
| **[!UICONTROL 发送文件]** | **[!UICONTROL opt+s]** | **[!UICONTROL *alt+s *]** | [将项目作为 CSV 或 PDF 文件发送给其他收件人](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL 安排文件导出]** | **[!UICONTROL *shift+opt+s *]** | **[!UICONTROL *shift+alt+s *]** | [按计划将项目作为 CSV 或 PDF 文件发送给其他收件人](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL 策划项目数据]** | **[!UICONTROL *shift+cmd+g *]** | **[!UICONTROL *shift+ctrl+g *]** | [策划项目数据](/help/analyze/analysis-workspace/curate-share/curate.md)。 |

| 帮助 | 描述 |
|---|---|
| **[!UICONTROL 视频]** | 在新浏览器选项卡中打开 Customer Journey Analytics YouTube 频道。 |
| **[!UICONTROL 帮助文档]** | 在新浏览器选项卡中打开（您刚才实际上正在阅读的…）文档。 |
| **[!UICONTROL 帮助论坛]** | 在新浏览器选项卡中打开 Adobe Analytics Experience League 社区论坛。 |
| **[!UICONTROL 热键]** | 显示您可以在 Workspace 中使用的热键（快捷方式）的概述。 |
| **[!UICONTROL 启用调试器]** | 启用调试器。您的项目将重新加载。 |
| **[!UICONTROL 禁用调试器]** | 禁用调试器。您的项目将重新加载。 |
| **[!UICONTROL 绩效]** | 显示一个对话框，其中显示有关 **[!UICONTROL Analysis Workspace 绩效]**&#x200B;的量度。使用&#x200B;**[!UICONTROL 下载为 CSV]**&#x200B;以下载绩效量度的 CSV 文件。 |
| **[!UICONTROL 关于 Workspace]** | 显示 **[!UICONTROL 关于 Analysis Workspace]** 对话框，其中包含版本信息、功能访问级别和活动功能标志。 |

## 数据源

您可以同步可视化内容，以控制哪个数据表或数据源对应于某项可视化内容。请参阅[管理数据源](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)，以了解详细信息。

## 使用 Analysis Workspace 


要开始使用 Analysis Workspace：

1. 登录到 [Adobe Experience Cloud](https://experience.adobe.com)。
1. 从界面右上角的应用切换器&#x200B;**[!UICONTROL 应用程序]**&#x200B;中选择 ![Customer Journey Analytics](/help/assets/icons/Apps.svg)。
1. 默认情况下将显示 Analysis Workspace 的&#x200B;**[!UICONTROL 项目]**&#x200B;页面。如果已为您选择了特定项目，或者您最近一直在处理该项目，则默认情况下会显示该项目。

### 创建项目

Analysis Workspace 中的分析被称作[项目](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)。

您可以在 Analysis Workspace 中创建项目，如[创建项目](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)中所述。

可以将项目组织到文件夹和子文件夹中，如 [Analysis Workspace 中的文件夹](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)中所述。

### 保存和共享项目

在 Analysis Workspace 中创建分析时，您的工作将[自动保存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)。

当您完成项目的构建并收集到可操作洞察时，其他人可能会想要使用这个项目。您可以与组织内的用户和组甚至组织外的人员共享项目。有关共享项目的信息，请参阅[共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md)。

## 其他资源 {#resources}

- Adobe 提供大量的 [Analytics 视频培训教程](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/overview)。
- 有关新功能的更新，请参阅 [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/zh-hans/docs/release-notes/experience-cloud/current)。



<!--
# Analysis Workspace overview {#analysis-workspace-overview}

Analysis Workspace allows you to build analyses quickly to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule [projects](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) with anyone you choose.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis workspace overview](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Interface

The following image and accompanying table explain the main elements in the Analysis Workspace user interface:

![Analysis Workspace window highlighting the various sections of the interface](assets/analysis-workspace-overview.png)

| Location | Name and function |
|:---------:|----------|
| A | Contains the name of the project, a menu structure to access functionality, a button ![Back button](/help/assets/icons/ChevronLeft.svg) to return back to your Project list, and a **[!UICONTROL Share]** button to [share your Workspace project](/help/analyze/analysis-workspace/curate-share/share-projects.md). <br/>Select the name of your project (for example: New project) at any time to change the name. <br/>Select ![Unfavor](/help/assets/icons/StarOutline.svg) to mark your project as a favorite project ![Favor](/help/assets/icons/Star.svg). |
| B | **Button panel:** Contains buttons for accessing the key [features](#features) of Analysis Workspace:<ul><li>![WebPage](/help/assets/icons/WebPage.svg) [[!UICONTROL Panels]](/help/analyze/analysis-workspace/c-panels/panels.md)</li><li>![Guided Analysis](/help/assets/icons/GuidedAnalysis.svg) [[!UICONTROL Guided Analysis]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL Visualizations]](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![Curate](/help/assets/icons/Curate.svg) [[!UICONTROL Components]](/help/components/overview.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL Table of contents]](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![Bookmark](/help/assets/icons/Bookmark.svg) [[!UICONTROL Data Dictionary]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **Left panel:** This area contains individual panels, visualizations, components, or lists. The content depends on the button selected in the button panel.  |
| D | **Canvas:** The main area where you drag content from the left panel to build your project. The project dynamically updates as you add panels, add visualizations to panels, and add components to visualizations. You can create multiple panels, and within each panel you can create multiple visualizations.<br/>Each panel is based on a selected data view. The selected data view determines available components like metrics and dimensions. See [Panels - Data view](/help/analyze/analysis-workspace/c-panels/panels.md#data-view) for more information. | 

## Features

The key features of Analysis Workspace are available through the button panel:

| Icon | Feature | Description |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL Panels]** | [Panels](/help/analyze/analysis-workspace/c-panels/panels.md) are used to organize your analysis within a project and can contain many tables & visualizations. Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. |
| ![Guided Analysis](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL Guided Analysis]** | [Guided analysis](../guided-analysis/overview.md) allows you to self-serve high quality data and insights about the customer journey through guided workflows. You can create an analysis for inclusion in your Workspace project, or include an existing analysis previously saved. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL Visualizations]** | [Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md), such as a bar or line chart, can be used to bring data visually to life. On the far left panel, select the middle **[!UICONTROL Visualizations]** icon to see the full list of visualizations available. |
| ![Curate](/help/assets/icons/Curate.svg) | **[!UICONTROL Components]** | [Components](/help/components/overview.md) include the following elements:<ul><li>![Dimensions](/help/assets/icons/Dimensions.svg) [Dimensions](/help/components/dimensions/overview.md)</li><li>![Event](/help/assets/icons/Event.svg) [Metrics](/help/components/apply-create-metrics.md)</li><li>![Segmentation](/help/assets/icons/Segmentation.svg) [Segments](/help/components/segments/seg-overview.md)</li><li>![Calendar](/help/assets/icons/Calendar.svg) [Date ranges](/help/components/date-ranges/overview.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL Table of contents]** | The table of contents organizes all panels and visualizations included in the project into a collapsible list, allowing you to access a specific panel or visualization quickly. |
|![Bookmark](/help/assets/icons/Bookmark.svg) | **Data dictionary** | The [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md) helps both users and administrators keep track of and better understand the components in their Analytics environment. |


## Menu

Most of the functionality of Analysis Workspace is available through drag and drop, and trough context menus within panels, visualizations and components.

Functionality is also available through the Workspace menu and shortcuts or hotkeys. Shortcut keys differ depending on the operating system that your browser is running on. See the tables below for an overview.  

Note that on your keyboard the following symbols might be used:

- **⇧** for **[!UICONTROL *shift*]**.
- **⌘** for **[!UICONTROL *cmd*]** (command).
- **⌃** for **[!UICONTROL *ctrl*]** (control).
- **⌥** for **[!UICONTROL *opt*]** (option).
- **⎇** for **[!UICONTROL *alt*]** (alternate).

See the tables below for an overview of the available menus.  

| **[!UICONTROL Project]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Create project]** | **[!UICONTROL *shift+cmd+p*]** | **[!UICONTROL *shift+ctrl+p*]** | Create a new project. |
| **[!UICONTROL Create a mobile scorecard]** | | | [Create a new mobile scorecard](/help/mobile-app/create-scorecard.md). |
| **[!UICONTROL Open...]** | **[!UICONTROL *cmd+o*]** | **[!UICONTROL *ctrl+o*]** | [Open an existing project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-another-project). |
| **[!UICONTROL Open previous version...]** | **[!UICONTROL *opt+cmd+o*]** | **[!UICONTROL *alt+ctrl+o*]** | [Open earlier versions of your project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version). |
| **[!UICONTROL Save]** | **[!UICONTROL *cmd+s*]** | **[!UICONTROL *ctrl+s*]** | [Save your project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-projects). |
| **[!UICONTROL Save with notes...]** | **[!UICONTROL *opt+cmd+s*]** | **[!UICONTROL *alt+ctrl+s*]** | [Add notes to the project version that you save](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Save as...]** | **[!UICONTROL *shift+cmd+s*]** | **[!UICONTROL *shift+ctrl+s*]** | [Save the project using a different name and details](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Refresh project]** | **[!UICONTROL *opt+r*]** | **[!UICONTROL *alt+r*]** | Refresh the project. |
| **[!UICONTROL Download CSV]** | **[!UICONTROL *shift+cmd+v*]** | **[!UICONTROL *shift+ctrl+v*]** | Download the project as a CSV file. |
| **[!UICONTROL Download PDF]**| **[!UICONTROL *shift+cmd+b*]** | **[!UICONTROL *shift+ctrl+b*]** | Download the project as a PDF document. |
| **[!UICONTROL Project info & settings]** | | | Define settings for your projects, such as name, tags, color palette, and more. |
| **[!UICONTROL User settings]** | | | [Configure preferences for using Analysis Workspace](/help/analyze/analysis-workspace/user-preferences.md). |


| **[!UICONTROL Edit]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Undo]** | **[!UICONTROL *cmd+z*]** | **[!UICONTROL *ctrl+z*]** | Undo the previous action. |
| **[!UICONTROL Redo]** | **[!UICONTROL *cmd+shift+z*]** | **[!UICONTROL *ctrl+shift+z*]** | Redo the previous action. |
| **[!UICONTROL Clear all]** | **[!UICONTROL *opt+w*]** | **[!UICONTROL *alt+w*]** | Clear all panels in the current project. | 

| **[!UICONTROL Insert]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Blank panel]** | **[!UICONTROL *opt+b*]** | **[!UICONTROL *alt+b*]** |  Insert a [Blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md). |
| **[!UICONTROL Media concurrent viewers]** | **[!UICONTROL *opt+h*]** | **[!UICONTROL *alt-h*]** |  Insert a [Media concurrent viewers](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md) panel. |
| **[!UICONTROL Media playback time spent]** | **[!UICONTROL *opt+i*]** | **[!UICONTROL *alt+i*]** |  Insert a [Media playback time spent](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) panel. |
| **[!UICONTROL Media average minute audience]** | **[!UICONTROL *opt+m*]** | **[!UICONTROL *alt+m*]** |  Insert a [Media average minute audience](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md) panel. | 
| **[!UICONTROL Attribution]** | **[!UICONTROL *opt+e*]** | **[!UICONTROL *alt+e*]** |  Insert an [Attribution](/help/analyze/analysis-workspace/c-panels/attribution.md) panel. |
| **[!UICONTROL Freeform]** | **[!UICONTROL *opt+a*]** | **[!UICONTROL *alt+a*]** |  Insert a [Freeform](/help/analyze/analysis-workspace/c-panels/freeform-panel.md) panel. |
| **[!UICONTROL Quick insights]** | **[!UICONTROL *opt+j*]** | **[!UICONTROL *alt+j*]** |  Insert a [Quick insights](/help/analyze/analysis-workspace/c-panels/quickinsight.md) panel. |
| **[!UICONTROL Experimentation]** |**[!UICONTROL *opt+x*]** | **[!UICONTROL *alt+x*]** |  Insert an [Experimentation](/help/analyze/analysis-workspace/c-panels/experimentation.md) panel. |
| **[!UICONTROL Freeform table]** | **[!UICONTROL *opt+1*]** | **[!UICONTROL *alt+1*]**|  Insert a [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) visualization. |
| **[!UICONTROL Line]** | **[!UICONTROL *opt+2*]** | **[!UICONTROL *alt+2*]** |  Insert a [Line](/help/analyze/analysis-workspace/visualizations/line.md) visualization. |
| **[!UICONTROL Bar]** | **[!UICONTROL *opt+3*]** | **[!UICONTROL *alt+3*]** |  Insert a [Bar](/help/analyze/analysis-workspace/visualizations/bar.md) visualization. |
| **[!UICONTROL Combo]** | **[!UICONTROL *opt+4*]**| **[!UICONTROL *alt+4*]** |  Insert a [Combo](/help/analyze/analysis-workspace/visualizations/combo-charts.md) visualization. | 


| **[!UICONTROL Components]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Create segment...]** | **[!UICONTROL *shift+cmd+e*]** | **[!UICONTROL *shift+ctrl+e*]** | Create a new [segment](/help/components/segments/seg-create.md). |
| **[!UICONTROL Create metric...]** | **[!UICONTROL *shift+cmd+c*]** | **[!UICONTROL *shift+ctrl+c*]** | Create a new [calculated metric](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Create date range...]** | **[!UICONTROL *shift+cmd+d*]** | **[!UICONTROL *shift+ctrl+d*]** | Create a new [date range](/help/components/date-ranges/overview.md). |
| **[!UICONTROL Create annotation...]** | **[!UICONTROL *shift+cmd+o*]** | **[!UICONTROL *shift+ctrl+o*]** | Create a new [annotation](/help/components/annotations/overview.md). |
| **[!UICONTROL Create audience...]** | **[!UICONTROL *shift+cmd+u*]** | **[!UICONTROL *shift+ctrl+u*]** | Create a new [audience](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Refewsh components]** | **[!UICONTROL *opt+shift+r*]** | **[!UICONTROL *alt+shift+r*]** | Refresh the components in the project. |

| **[!UICONTROL Share]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Share with Workspace users]** | **[!UICONTROL *cmd+h*]** | **[!UICONTROL *ctrl+h*]** | [Share the project with other Workspace users](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization). |
| **[!UICONTROL Share with anyone]** | **[!UICONTROL *opt+l*]** | **[!UICONTROL *alt+l*]**| [Share a read-only version of the project with anyone](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project). |
| **[!UICONTROL Send file]** | **[!UICONTROL opt+s]** | **[!UICONTROL *alt+s*]** | [Send the project as a CSV or PDF file to other recipients](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Schedule file export]** | **[!UICONTROL *shift+opt+s*]** | **[!UICONTROL *shift+alt+s*]** | [Send the project on a schedule as a CSV or PDF file to other recipients](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). | 
| **[!UICONTROL Curate project data]** | **[!UICONTROL *shift+cmd+g*]** | **[!UICONTROL *shift+ctrl+g*]** | [Curate the project data](/help/analyze/analysis-workspace/curate-share/curate.md). |

| Help | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Videos]** | | | Open the Customer Journey Analytics YouTube channel in a new browser tab. |
| **[!UICONTROL Help documentation]** | | | Open the documentation (you are actually reading just now...) in a new browser tab. |
| **[!UICONTROL Help forum]** | | | Open the Adobe Analytics Experience League communities forum in a new browser tab. |
| **[!UICONTROL Hotkeys]** | | | Show an overview of the hotkeys (shortcuts) you can use in Workspace. |
| **[!UICONTROL Enable debugger]** |  | | Enable the debugger. Your project will reload. | 
| **[!UICONTROL Disable debugger]** | | | Disable the debugger. Your project will reload. |
| **[!UICONTROL Performance]** | | | Show a dialog displaying metrics on the **[!UICONTROL Analysis Workspace performance]**. Use **[!UICONTROL Download as CSV]** to download a CSV file of the performance metrics. |
| **[!UICONTROL About Workspace]** | | | Show an **[!UICONTROL About Analysis Workspace]** dialog with version information, feature access levels and active feature flags. |

## Data sources

You synchronize visualizations to control which data table or data source corresponds to a visualization. See [manage data sources](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) for more information.

## Use Analysis Workspace


To start using Analysis Workspace: 

1. Log in to [Adobe Experience Cloud](https://experience.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** from the app switcher ![App](/help/assets/icons/Apps.svg) at the top right of the interface.
1. The **[!UICONTROL Projects]** page of Analysis Workspace is shown by default. If a specific project has been selected for you or you have been working on recently, then that project is shown by default.

### Create a project

An analysis in Analysis Workspace is referred to as a [project](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md). 

You can create a project in Analysis Workspace as described in [Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Projects can be organized into folders and subfolders, as described in [Folders in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Save and share a project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, others might want to consume the project. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).

## Additional resources {#resources}

- The [Learning landing](/help/getting-started/landing.md#learning) page in Customer Journey Analytics. This page is  great way to become acquainted with Analysis Workspace. Especially the Learning Workspace Fundamental. This template walks you through common terminology and steps for building your first analysis in Workspace
- Adobe offers hundreds of [Analytics video training tutorials](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/overview).
- See [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/zh-hans/docs/release-notes/experience-cloud/current) for updates about new features.



<!--
# Analysis Workspace overview

Analysis Workspace allows you to quickly build analyses to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule projects with anyone you choose.

The following video provides a brief overview with examples of what is possible.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace overview](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Areas of Analysis Workspace

The following image and accompanying table explain some of the main areas in Analysis Workspace:

![Analysis Workspace overview](assets/analysis-workspace-overvew.png)

| Location in image | Name and function |
|---------|----------|
| A | **Far left rail:** Contains tabs for adding panels, visualizations, and components to Analysis Workspace. Also contains the Data Dictionary icon that is used to open the Data Dictionary. |
| B | **Left rail:** Depending on which tab is selected in the far left rail, this area contains individual panels, visualizations, or components. |
| C | **Canvas:** This is the main area where you drag content from the left rails to build your project. The project dynamically updates as you add panels, visualizations, and components to the canvas. | 
| D | **Report suite drop-down menu:** For each panel in Analysis Workspace, the report suite drop-down menu allows you to choose the report suite that you want to use as your data source. | 

## Features in Analysis Workspace {#analysis}

Following are some of the key features available in Analysis Workspace: 

### Panels

**Panels** are used to organize your analysis within a project and can contain many tables & visualizations. Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. On the far left rail, select the top **[!UICONTROL Panels]** icon to see a full list of panels available.

To learn more about panels, see [Panels overview](/help/analyze/analysis-workspace/c-panels/panels.md).

![](assets/build-panels.png)

### Visualizations

**Visualizations**, such as a bar or line chart, can be used to visually bring data to life. On the far left rail, select the middle **[!UICONTROL Visualizations]** icon to see the full list of visualizations available. 

To learn more about visualizations, see [Visualizations overview](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

![](assets/build-visualizations.png)

### Components

Components in Analysis Workspace consist of the following:

* Dimensions

* Metrics

* Segments

* Date ranges

To learn more about each of these component types, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). 

Each of these component types can be added to a visualization (such as a Freeform table) to start answering your business questions. 

After you understand component terminology, you can drag components into visualizations (including Freeform tables) to [build your analysis](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

![](assets/build-components.png)

### Data Dictionary

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment.

To learn more about the Data Dictionary, see [Data Dictionary overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

### Data Sources

Synchronizing visualizations lets you control which data table or data source corresponds to a visualization. Here is more information on how you can [manage data sources](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md).

## Start using Analysis Workspace

### Log in to Adobe Analytics {#login}

To start using Analysis Workspace, log in to Adobe Analytics by going to [experience.adobe.com/analytics](https://experience.adobe.com/analytics). The Projects page of Analysis Workspace is shown by default. If a specific project has been selected for you, that project is shown by default.

### Create a project {#new-project}

An analysis in Analysis Workspace is referred to as a [project](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).  

You can create a project in Analysis Workspace as described in [Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Projects can be organized into folders and subfolders, as described in [Folders in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Save and share a project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, the project is ready to be consumed by others. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).

## Additional resources {#resources}

* Adobe offers hundreds of [Analytics video training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/overview.html?lang=zh-Hans).
* See [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans#analytics) for updates about new features.
* A great way to become acquainted with Analysis Workspace is through the Analysis Workspace Training Tutorial template. This template walks you through common terminology and steps for building your first analysis in Workspace. To begin the tutorial:
  1. On the [!UICONTROL **Workspace**] tab in Adobe Analytics, select **[!UICONTROL Learning]** on the left.
  1. Select **[!UICONTROL Open Tutorial]**.
     ![](assets/training-tutorial.png)

-->