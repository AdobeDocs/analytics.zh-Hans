---
description: 了解在Analysis Workspace中创建项目的基础知识
title: 创建项目
feature: Workspace Basics
role: User, Admin
exl-id: 6130b1d8-078c-46d8-9fce-eb39739a9570
source-git-commit: f7bd5eaffd4502510451e3afb5929682ad967ecb
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 5%

---

# 创建项目

[项目](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) 在Analysis Workspace中，您可以查看业务关键型分析，这些分析可以与组织内部或外部的利益相关者共享。

有关如何开始使用Analysis Workspace的一般信息，请参阅 [Analysis Workspace概述](/help/analyze/analysis-workspace/home.md).

以下部分介绍了如何创建项目并开始为任何Analysis Workspace项目添加关键构建块：面板、可视化图表和组件。

## 从空白项目或报表创建项目

1. 在Adobe Analytics中，选择 [!UICONTROL **工作区**].

1. 选择创建空白项目还是从报表创建项目：

   +++创建空白项目

   1. 在 [!UICONTROL **工作区**] 选项卡，选择 [!UICONTROL **项目**] 选项卡，然后选择 [!UICONTROL **创建项目**].

   1. 选择创建空白项目还是空白移动记分卡

      * **空白项目** 如果您计划从浏览器共享您的分析
      * [**空白移动记分卡**](/help/analyze/mobile-app/curator.md) 如果您计划从Adobe Analytics功能板移动应用程序共享您的分析。

   1. 选择&#x200B;[!UICONTROL **创建**]。

+++

   +++从报表创建项目

   1. 在 [!UICONTROL **工作区**] 选项卡，选择 [!UICONTROL **报告**] 选项卡。

   1. 搜索或导航到要使用的报告，然后在该报告出现时将其选定。

      默认情况下提供一组标准报表。 此外，您的组织可能已创建了自定义报告供您选择。

   1. 选择 [!UICONTROL **项目**] > [!UICONTROL **保存**] 以将报表另存为新项目。

      有关报表的更多信息，请参阅中的“导航报表选项卡” [Adobe Analytics登录页面](/help/analyze/landing.md).

+++

1. 接下来，您需要向项目中添加面板、可视化图表和组件。 首先，在Analysis Workspace中将面板添加到您的项目，如中所述 [在项目中添加面板](#add-panels-to-the-project). 然后，您可以将可视化图表添加到任何面板。 最后，您可以将组件添加到任何面板或可视化图表中。

## 在项目中添加面板 {#panels}

[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hans) 是Analysis Workspace中任何项目的基础。 面板用于组织项目的内容（可视化和组件）。

Analysis Workspace 中提供的许多面板都可以基于一些用户输入来生成整套分析。

要添加面板，请执行以下操作：

1. 选择 [!UICONTROL **面板**] 图标。

   ![](assets/build-panels.png)

1. 搜索要添加的面板。 当它显示在左边栏中时，将其拖动到您的项目中。

1. 向面板中添加可视化图表，如中所述 [向项目添加可视化图表](#add-visualizations-to-the-project).

   或者，也可以将组件直接添加到面板，如中所述 [将组件添加到项目](#add-components-to-the-project).

## 向项目添加可视化图表

[可视化图表](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hans) （例如自由格式表、条形图或折线图）可用于直观地将数据呈现出来。

>[!TIP]
>
>自由格式表是最常见的可视化类型，是交互式数据分析的基础。 有关如何在Analysis Workspace中使用自由格式表的更多详细信息，请参阅 [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

要添加可视化图表，请执行以下操作：

1. 选择 **[!UICONTROL 可视化图表]** 图标。

   ![](assets/build-visualizations.png)

1. 搜索要添加的可视化图表。 当它显示在左边栏中时，将其拖动到项目中的面板。

1. 将组件添加到可视化图表，如中所述 [将组件添加到项目](#add-components-to-the-project).

## 将组件添加到项目

[组件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) 构成任何项目的实际数据。 您可以将组件添加到可视化图表或面板。

>[!TIP]
>
>有关每个组件的信息，请在左边栏中选择组件名称旁边的信息图标，或参阅 [Analytics组件指南](/help/components/home.md).

要添加组件，请执行以下操作：

1. 选择 **[!UICONTROL 组件]** 图标。

   ![](assets/build-components.png)

1. 搜索要添加的组件。 当它显示在左边栏中时，将其拖动到项目中的面板或可视化图表中。

1. （可选）按照中的说明共享项目 [保存并共享项目](#save-and-share-the-project).

## 保存并共享项目

在Analysis Workspace中创建分析时，您的工作是 [自动保存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

当您完成项目构建并收集可操作见解时，项目便可供其他人使用。 您可以与组织中的用户和组共享项目，甚至可以与组织外部的人员共享项目。 有关共享项目的信息，请参见 [共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md).
