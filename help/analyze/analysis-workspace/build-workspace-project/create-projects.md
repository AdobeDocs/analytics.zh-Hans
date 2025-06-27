---
description: 了解如何在Analysis Workspace中创建项目。
title: 创建项目
feature: Workspace Basics
role: User, Admin
exl-id: 24193013-1361-43fc-b129-c44f207d9101
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 90%

---

# 创建项目 {#create-projects}


使用 Analysis Workspace 中的[项目](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)可以创建和查看业务关键分析。这些分析可以与组织内部或外部的利益相关者共享。

1. 在 Adobe Analytics 中，选择 **[!UICONTROL Workspace]**。

1. 选择左侧面板中的&#x200B;**[!UICONTROL 项目]**，然后选择&#x200B;**[!UICONTROL 创建项目]**。

1. 选择&#x200B;**空白 Workspace 项目**，以使用浏览器创建您的 Workspace 项目。

   有关如何创建移动记分卡项目的更多信息，请参阅[空白移动记分卡](/help/analyze/mobile-app/curator.md)，您可以使用移动应用程序与其他利益相关者共享该项目。

1. 选择&#x200B;[!UICONTROL **创建**]。


现在您已经创建了一个空白 Workspace 项目，请确保您熟悉 [Analysis Workspace](/help/analyze/analysis-workspace/home.md) 用户界面。完成后，您就可以构建您的项目了。操作方法：

![Example project](assets/example-project.png)

* 将[面板](/help/analyze/analysis-workspace/c-panels/panels.md)添加到您的项目中。例如，**[!DNL Example Panel]** ➊。

* 在您的面板中添加[可视化效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。例如：
   * **[!DNL Line]** [线形图](/help/analyze/analysis-workspace/visualizations/line.md)可视化图表➋
   * **[!DNL US States]** [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)可视化图表➌
* 在可视化效果中添加[组件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)例如：
   * **[!DNL US States]** [维度](/help/components/dimensions/overview.md) ➍
   * **[!DNL Unique Visitors]** [量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md) ➎
   * **[!DNL Average Revenue Per Order]** [计算量度](/help/components/c-calcmetrics/cm-overview.md) ➏
   * **[!DNL Visits from Mobile Devices]** [区段](/help/components/segmentation/seg-overview.md) ➐
   * **[!DNL Last Month]** [日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) ➑
   * **[!DNL Example]** [注释](/help/analyze/analysis-workspace/components/annotations/overview.md) ➒


## 项目信息和设置 {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="计数重复实例"
>abstract="指定是否将重复实例计入报告中。<br/><br/>注意：此设置不适用于“流”或“流失”可视化。"

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="计数重复实例"
>abstract="指定是否将重复实例计入报告中。<br/>注意：此设置不适用于“流”或“流失”可视化。"


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="允许评论"
>abstract="启用后，Analysis Workspace 中项目的右侧栏中会显示一个评论区域。"


项目设置提供有关当前活动项目的项目级信息。

![The Project Info &amp; Settings window.](./assets/projectinfo.png)

这些设置包括：

| 设置 | 描述 |
|---|---|
| 项目名称 | 给项目起的名称。您可以双击该名称以编辑它。 |
| 所有者 | 项目所有者名称。 |
| 最近修改 | 项目上次修改日期。 |
| 标记 | 列出应用于项目以方便分类的所有标记。 |
| 描述 | 描述有助于明确项目的目的。您可以双击描述以编辑它。 |
| 计数重复实例 | 指定是否将重复实例计入报告中。注意：此设置不适用于“流”或“流失”可视化。 |
| 显示注释 | 指定是否显示该项目的注释。 |
| [项目调色板](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md) | 通过从已为色盲优化过的现成调色板中进行选择或通过指定您的自定义调色板，可更改在 Workspace 中使用的类别调色板。此功能影响 Workspace 中的许多内容，包括大多数可视化。 |
| [视图密度](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | 通过减小左侧面板、自由格式表和同类群组表的垂直边距，让您可在屏幕上看到更多数据。 |



<!--
# Create projects in Analysis Workspace

[Projects](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace allow you to view business-critical analyses that can be shared with stakeholders inside or outside your organization. 

For general information about how to get started using Analysis Workspace, see [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md).

The following sections describe how to create a project and start adding the key building blocks for any Analysis Workspace project: panels, visualizations, and components.

## Create a project from a blank project or a report

1. In Adobe Analytics, select [!UICONTROL **Workspace**].

1. Choose whether to create a blank project or to create a project from a report:

   +++Create a blank project

   1. On the [!UICONTROL **Workspace**] tab, select the [!UICONTROL **Projects**] tab on the left side of the page, then select [!UICONTROL **Create project**].

   1. Choose whether to create a blank project or a blank mobile scorecard

      * **Blank project** if you plan to share your analysis from the browser 
      * [**Blank mobile scorecard**](/help/analyze/mobile-app/curator.md) if you plan to share your analysis from the Adobe Analytics dashboards mobile app.

   1. Select [!UICONTROL **Create**].

   +++

   +++Create a project from a report
   
      1. On the [!UICONTROL **Workspace**] tab, select the [!UICONTROL **Reports**] tab on the left side of the page.

      1. Search for or navigate to the report you want to use, then select it when it appears.

          A set of standard reports is available by default. In addition, your organization might have created custom reports for you to choose from.
          
      1. Select [!UICONTROL **Project**] > [!UICONTROL **Save**] to save the report as a new project.

          For more information about reports, see "Navigate the Reports tab" in [Adobe Analytics landing page](/help/analyze/landing.md).

   +++

1. Next, you need to add panels, visualizations, and components to your project. First, add panels to your project in Analysis Workspace, as described in [Add panels to the project](#add-panels-to-the-project). You can then add visualizations to any panels. Finally, you can add components to any panels or visualizations.

## Add panels to the project {#panels}

[Panels](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) are the foundation to any project in Analysis Workspace. Panels are used to organize the content (visualizations and components) of a project. 

Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. 

To add a panel:

1. Select the [!UICONTROL **Panels**] icon in the left rail.

   ![](assets/build-panels.png)

1. Search for the panel you want to add. When it appears in the left rail, drag it into your project.

1. Add visualizations to your panel, as described in [Add visualizations to the project](#add-visualizations-to-the-project). 

   Alternatively, you can add components directly to a panel, as described in [Add components to the project](#add-components-to-the-project).

## Add visualizations to the project

[Visualizations](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) (such as a freeform table, a bar chart, or a line chart) can be used to visually bring data to life. 

>[!TIP]
>
>Freeform tables are the most common type of visualization, and are the foundation for interactive data analysis. For more details about how to work with Freeform tables in Analysis Workspace, see [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

To add a visualization:

1. Select the **[!UICONTROL Visualizations]** icon in the left rail.

   ![](assets/build-visualizations.png)

1. Search for the visualization you want to add. When it appears in the left rail, drag it to a panel within your project. 

1. Add components to the visualization, as described in [Add components to the project](#add-components-to-the-project).

## Add components to the project

[Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) make up the actual data of any project. You can add components to visualizations or to panels.

>[!TIP]
>
>For information about each component, select the Info icon next to a component's name in the left rail, or see the [Analytics Components Guide](/help/components/home.md).

Following is basic information about how to add a component to a project in Analysis Workspace. For more detailed information about adding the various types of components (dimensions, metrics, segments, and date ranges), see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

To add a component to a project in Analysis Workspace:

1. Select the **[!UICONTROL Components]** icon in the left rail.

   ![](assets/build-components.png)

1. Scroll to or search for the component you want to add, then drag it to a panel or visualization within your project. 

   For example, you can drag a segment to the segment drop zone in a panel header.

   ![drop a segment in the drop zone](assets/segment-dropzone.png)

   For more information about adding components to projects, see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

1. (Optional) Share the project as described in [Save and share the project](#save-and-share-the-project).

## Save and share the project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, the project is ready to be consumed by others. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).
-->