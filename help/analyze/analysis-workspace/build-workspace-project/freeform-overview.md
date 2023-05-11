---
description: 学习在 Workspace 项目中工作的基础知识。
keywords: Analysis Workspace
title: 项目概述
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: 7b3acbab3f65b02ceaaea154fb6152cfb0bf07f0
workflow-type: tm+mt
source-wordcount: '1531'
ht-degree: 81%

---

# 项目概述

通过 Workspace 项目，可结合数据组件、表格和可视化以得出您的分析结果，并与您组织中的任何人共享。在开始您的第一个项目之前，请了解如何访问、浏览和管理您的项目。

以下是一段关于如何构建 Workspace 项目的视频：

>[!VIDEO](https://video.tv.adobe.com/v/334076/?quality=12)

## 项目列表 {#project-list}

当您首次转到&#x200B;**[!UICONTROL “Analytics”]**>**[!UICONTROL “Workspace”]**&#x200B;时，该页面列出您拥有或与您共享的所有项目。这也是 Adobe Analytics 的登陆页面，除非您以前设置过自定义登陆页面。

![](assets/sample-project.png)

“项目”页面包含以下信息：

>[!NOTE]
>
>默认情况下，某些列不显示。 要自定义您看到的列，请单击 **自定义表** 图标 ![自定义表](assets/projects-page-customize-columns-icon.png).


| 元素 | 描述 |
|---|---|
| [编辑偏好设置](/help/analyze/analysis-workspace/user-preferences.md) | 管理您创建的所有新项目或面板的Analysis Workspace及其相关组件的设置。 |
| [创建文件夹](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | 向项目和文件夹列表中添加新文件夹或子文件夹。 |
| [创建项目](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | 从头开始或从报表开始启动新项目。 |
| 展开 | 显示用于创建空白项目或移动记分卡的选项， [查看培训教程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=zh-Hans)或 [查看发行说明](/help/release-notes/latest.md). |
| 显示文件夹和项目 | 选择是否显示项目的文件夹结构。 有关更多信息，请参阅[关于 Analytics 中的文件夹](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)。 |
| 自定义表（图标） | 允许您自定义在“项目”页面上为每个项目显示的信息。 |
| 名称 | Workspace 项目名称。 |
| 类型 | 指示这是工作区项目、文件夹还是 [移动记分卡](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=zh-Hans). |
| 标记 | 应用于项目的标记。 |
| 已计划 | 指示是否计划按计划通过电子邮件将项目发送给收件人。 请参阅 [计划项目](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| 共享链接（任何人） | 项目可以与任何人共享 — 即使是与无权访问Analysis Workspace的人共享。 此列显示项目是否已通过这种方式共享。 请参阅 [与任何人共享项目（无需登录）](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md) 以了解更多信息。 |
| 报表包 | 与项目关联的报表包。 |
| [项目角色](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans) | 指示您在项目中的角色 — 所有者、编辑、复制、查看。 |
| 所有者 | 创建此项目的人员（您或与您共享此项目的人员）。 |
| 共享对象 | 与项目共享的用户。 |
| 上次修改时间 | 项目上次修改的日期和时间。 |
| 上次打开 | 项目上次打开的日期和时间。 |
| 项目ID | 项目的ID。 |
| Longest Date Range | 项目的最长日期范围。 |
| 查询次数 | 项目中包含的查询总数。 |
| 位置 | 项目所在的文件夹。 |

## 菜单栏 {#menu-bar}

在项目中，菜单提供管理项目、添加组件、查找帮助等选项。还可通过键盘[快捷方式](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=zh-Hans)访问每个菜单选项。

![](assets/menu.png)

| 菜单项 | 描述 |
|---|---|
| 项目 | 包括用于项目管理的常见操作，包括“新建”、“打开”、“保存”、“另存为”和 [另存为公司报表](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). 还可通过单击“刷新项目”而刷新整个项目以检索最新的数据和定义。通过[“下载 CSV 和 PDF”](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hans)选项，可从 Workspace 导出数据。[“项目信息和设置”](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html?lang=zh-Hans?#info-settings)提供多种用于管理项目的选项。 |
| 编辑 | 撤消或重做您的上一项操作。“全部清除”将您的项目重置为空起点。 |
| 插入 | 从此菜单插入新面板或可视化图表。还可从左侧边栏插入新面板和可视化图表。 |
| [组件](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=zh-Hans) | 从您的项目创建新区段、计算指标、日期范围或警报组件。还可从左侧边栏创建新组件。如果最近更改了组件定义，则“刷新组件”将检索最新定义。 |
| [共享](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html?lang=zh-Hans) | 策划、安排 PDF/CSV 项目以及将其共享给您组织中的接收方。 |
| 帮助 | 访问帮助文档、视频和 Analytics [Experience League 社区](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)。管理 Workspace 提示和[调试器](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md)的可见性。查找关于 Workspace 及影响项目[性能](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html?lang=zh-Hans)的各种因素的详细信息。 |
| “共享”按钮或“所有者” | 如果您处于项目的“拥有”或“编辑”角色，则通过右上方的“共享”按钮可一键管理项目接收方。如果您处于项目的“复制”或“查看”角色，则您将看到项目所有者的姓名。 |

### 项目信息和设置 {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL 项目]** > **[!UICONTROL 项目信息和设置]** 提供有关当前活动项目的项目级信息。

![](assets/projectinfo.png)

这些设置包括：

| 设置 | 描述 |
|---|---|
| 项目名称 | 给项目起的名称。您可以双击该名称以编辑它。 |
| 创建者 | 项目所有者名称。 |
| 上次修改时间 | 项目上次修改日期。 |
| 标记 | 列出应用于项目以方便分类的所有标记。 |
| 描述 | 描述有助于明确项目的目的。您可以双击描述以编辑它。 |
| 计算项目中的重复实例 | 指定是否将重复实例计入报表中。例如，此设置（激活时）会将同一页面的多次连续页面浏览视为多次页面浏览。关闭此设置后，它们会计为单次页面浏览（这仅会影响某些量度，例如单页面浏览量）。**注意**：此设置不适用于“流”或“流失”可视化。 |
| [项目调色板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=zh-Hans) | 通过从已为色盲优化过的现成调色板中进行选择或通过指定您的自定义调色板，可更改在 Workspace 中使用的类别调色板。此功能影响 Workspace 中的许多内容，包括大多数可视化。 |
| [视图密度](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hans) | 通过减小左侧边栏、自由格式表和同类群组表的垂直边距，让您可在屏幕上看到更多数据。 |

## 左侧边栏 {#left-rail}

在项目中，可从左侧边栏访问[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hans)、表格、[可视化](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hans)和[组件](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=zh-Hans)。这些都是项目的构建基块。

还可从[空面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=zh-Hans)访问可视化和面板。

左侧边栏中的组件（维度、指标、区段、日期范围）与活动面板报表包相关。活动面板在自身四周将有蓝色边框，而活动报表包将列在组件边栏的顶部。

![](assets/left-rail.png)

## 右键单击菜单

以下是一段关于在 Analysis Workspace 中使用右键单击菜单的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23981/?quality=12)

## 项目画布 {#canvas}

项目画布是将面板、表格、可视化和组件集中在一起以构建您的分析的地方。一个项目可包含许多面板，而每个面板均可包含许多表格和可视化。

当您要根据时段、报表包或分析用例组织您的项目时，面板非常有用。活动面板在自身四周将有蓝色边框，并决定在左侧边栏中有哪些组件可用。

根据您为项目选择的起点，您在画布中将首先使用[自由格式表](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=zh-Hans)或[空面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=zh-Hans)。最快开始分析的方法是选择一个或多个组件，然后将其拖放到项目画布中。随后将自动为您呈现数据表。[详细了解](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=zh-Hans)构建表的不同选项，或利用我们的[培训教程](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans?#training-tutorial)就构建您的第一个项目获得更多指导。

![](assets/canvas.png)

## 项目管理器 {#manager}

可在 **[!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 项目]**&#x200B;下管理 Analysis Workspace 项目。 项目管理器显示特定用户已创建的项。

可在[!UICONTROL 管理员] > [!UICONTROL Analytics 用户和资源] > [!UICONTROL 转移资产]下将项目所有权移交给新用户。

在项目管理器中，可执行添加、标记、共享、复制等操作。可在搜索栏中或通过使用左侧边栏中的过滤器选项搜索项目。可按标记、所有者、项目类型等进行筛选。

![](assets/project-manager.png)

以下是项目管理器中的常用操作，可同时对一个或多个项目执行此类操作：

| 操作 | 描述 |
|---|---|
| 添加 | 从头开始创建新项目或从 [报告](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). |
| 标记或批准 | 选择“标记”或“批准”以组织项目并使其更易于搜索。 |
| [共享](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans) | 使项目可供您所在组织中的其他 Analysis Workspace 用户使用。 |
| 删除 | 删除项目。 |
| 重命名 | 编辑项目的名称。 |
| 复制 | 创建项目的副本。此操作创建新项目和项目 ID。其中不复制与原始项目关联的任何共享或时间表。 |
| 导出到 CSV | 将项目下载为 CSV 文件，其中包括纯文本数据。 |
