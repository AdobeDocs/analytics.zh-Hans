---
description: 'null'
keywords: Analysis Workspace
title: 创建项目 - 概述
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 创建项目 - 概述

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

您可以根据可视化、报表组件和数据表的任意组合创建可靠的Analytics项目。 它将临时分析中的许多表构建器功能引入到Analytics中。

在分析工作区中，您可以以以前不可能的方式比较和剖析数据。 例如，配置排名报告并立即对数据查询进行迭代更改，然后访问和操作报告级别的值。

该查询直接转到报告引擎——您可以在行中进行更改，而无需显示其他报告来创建分析。 结果将立即返回，而不刷新浏览器。

## 工作区项目列表页 {#section_39AA007D7C384F4E869F842F1C7B11F8}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been granted access to. You can set this page to be your Adobe Analytics landing page by clicking **[!UICONTROL Set as Landing Page]**. (如果您未看到此选项，就像在下面的屏幕快照中一样，它已经是您的登陆页。)

![](assets/sample-project.png)

“工作区项目列表”页面包含以下信息：

| 元素 | 描述 |
|---|---|
| 项目模 [板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) | 您可以按原样使用这些预填充的项目模板，或根据您的需求（例如，通过添加或替换指标或可视化）调整它们，然后使用新名称保存它们。 |
| [新建项目](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) | 单击此链接可从头开始开始新项目。 |
| 管理项目 | Clicking this link takes you to the Projects Component Manager ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), which lists all your projects and lets you tag, share, delete, rename, approve, copy, and export projects to CSV. |
| 视图教程 | 带您观看 [分析工作区YouTube视频](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)。 |
| 名称 | 工作区项目的名称。 |
| 创建者 | 创建此项目的人员（您或与您共享项目的人员）。 |
| 标记 | 在“项目组件管理器”中或在 **[!UICONTROL Workspace]** > **[!UICONTROL Project]** >下应用到项目的标记 **[!UICONTROL Project Info & Settings]**。 |
| 上次修改时间 | 上次修改项目的日期和时间。 |

## 项目信息和设置 {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** 提供有关当前活动项目的项目级信息。

| 设置 | 描述 |
|---|---|
| 项目名称 | 给予项目的名称。 您可以多次单击该名称进行编辑。 |
| 创建者 | 项目所有者名称 |
| 上次修改时间 | 上次修改项目的日期。 |
| 标记 | 列表应用于项目的任何标记，以便更轻松地分类。 您还可以在保存项目时标记项目。 在“工作区”登陆页的列中视图项目的标 [!UICONTROL Tags] 记。 |
| 描述 | 说明有助于明确项目目的。 您可以多次单击说明以进行编辑。 |
| 计数项目中的重复实例 | 指定是否在报表中计算重复实例的数量。如果同一变量有多个连续值，则可以将它们计为一个或多个变量实例。 |
| 可视化颜色方案 | 您可以通过从其他调色板中进行选择或指定自己的调色板来更改Workspace中使用的颜色方案。 此功能影响Workspace中的许多内容，包括大多数可视化。 |
| 视图密度 | 您可以减小左边栏、自由格式表和同类群组表的垂直边距，从而在屏幕上查看更多数据。 |

## 项目菜单 {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

顶部的“项目”菜单如下所示：

![](assets/new-project-menus.png)

子菜单包含以下选项。

>[!NOTE] 标有星号 (*) 的选项仅在&#x200B;**已保存**&#x200B;项目中显示。

| 项目 | 编辑 | 插入 | 组件 | 共享 | 帮助 |
|---|---|---|---|---|---|
| 新建 | 撤消 | 新面板 | 新区段 | 共享项目 | 视频 |
| Open | 清除 | 全新的自由格式面板 | 新指标 | 获取项目链接* | 热键 |
| 保存 | 全部清除 | 新的区段比较面板 | 新日期范围 | 立即发送文件* | 帮助论坛 |
| 另存为* |  | 新的自由格式表 | 新警报 | 在计划时发送文件* |  |
| 设置为登陆页面* |  | 新行 | 刷新组件 | 策划项目数据 |  |
| 刷新项目 |  | 新建栏 |  |  |  |
| 下载CSV |  |  |  |  |  |
| 下载 PDF* |  |  |  |  |  |
| 项目信息和设置 |  |  |  |  |  |

## 左边栏 {#section_271295C26EC840ABB2A8E7EC0498B60E}

左边栏含有 3 个图标，允许您一键访问面板、[可视化](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)和[组件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)（维度、量度、区段、数据范围）：

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** was added to the list of panels accessible from the left rail. 要创建&#x200B;**新的同类群组面板**，请拖入一个空白面板，然后再拖入一个同类群组表可视化。
