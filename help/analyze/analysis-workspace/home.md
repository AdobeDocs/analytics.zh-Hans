---
description: 如何开始使用 Adobe Analytics。
keywords: Analysis Workspace
title: 入门指南
topic: Reports and analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Analysis Workspace

Analysis Workspace 是 Adobe 的一款旗舰工具，可用于为您的组织制定基于数据的可操作决策。通过自由格式表（最常见的可视化图表），您可以使用维度、量度、区段和日期范围轻松创建自定义报表。

## 先决条件

[使用 Adobe Experience Platform Launch 将数据发送到 Adobe Analytics](/help/implement/implement-with-launch/validate-publish-prod.md)：使用 Analysis Workspace 需要有效的实施。在使用这款工具之前，请确保您的组织正在向 Adobe 发送数据。其他实施（如 DTM 或旧版手动实施）也可以正常工作。

## 在工作区中提取基本的排名报表

使用 Analysis Workspace 提取基本的排名报表。排名报表会显示每个维度值的聚合总视图，其中最先显示最大值。这些类型的报表有助于查看网站中的哪些组件最有效，例如，哪些页面的流量最大，或者哪些产品销量最高。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
3. 在顶部导航栏中，单击“工作区”。
4. 单击“新建项目”按钮。
5. 在模态弹出窗口中，确保选择“空白项目”，然后单击“创建”。
6. 在左侧，您应该会看到维度、量度、区段和日期范围的列表。找到“页面”维度（橙色），并将其拖动到画布上，其中显示“将维度放置在此处”。
7. 请注意，如果报表包包含数据，则可以看到显示当月热门页面的报表。Analysis Workspace 会自动使用[发生次数](/help/components/c-variables/c-metrics/metrics-occurrences.md)量度填充报表。
8. 找到“访问次数”量度（绿色），将其拖动到“发生次数”量度标头的&#x200B;**上面**&#x200B;或&#x200B;**旁边**（避免将“访问次数”量度置于“发生次数”的上方）。如果将“访问次数”量度拖动到“发生次数”的上方，则报表中的“发生次数”量度会被替换。如果将“访问次数”量度拖动到“发生次数”旁边，则这两个量度会并排显示。
9. 如果要保存项目，请单击左上角菜单中的&#x200B;*[!UICONTROL 项目]&gt;[!UICONTROL 保存]*。

## 在工作区中提取基本的趋势报表

使用 Analysis Workspace 提取基本的趋势报表。趋势报表使用选定日期范围显示一段时间的量度视图。这些类型的报表有助于确定一段时间内的趋势，并且可用于衡量业务决策的成败。例如，您可以查看一段时间的页面查看次数趋势报表，以便了解网站重新设计是否有助于增加流量或减少流量。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
3. 在顶部导航栏中，单击“工作区”。
4. 单击“新建项目”按钮。
5. 在模态弹出窗口中，确保选择“空白项目”，然后单击“创建”。
6. 在左侧，您应该会看到维度、量度、区段和日期范围的列表。找到“页面查看次数”维度，并将其拖动到画布上标有“在此处放置量度”的小空间。请勿将其放置在为维度保留的空间中（至少对于本次练习）。
7. 请注意，如果报表包包含数据，您应该会看到一个当月页面查看次数趋势报表。Analysis Workspace 会自动引入“日”日期范围，以便您可以查看当月页面查看次数趋势。
8. 在左侧的日期范围组件列表中找到“周”日期范围（紫色）。单击日期范围标题可展开并查看所有日期范围组件，或使用搜索栏。
9. 将“周”日期范围拖动到画布上的“日”日期范围标题上方可将其替换。
10. 请注意，现在按“周”而不是按“日”来汇总您的趋势报表。
11. 如果要保存项目，请单击左上角菜单中的&#x200B;*[!UICONTROL 项目]&gt;[!UICONTROL 保存]*。

## 试用该工具

由于 Analysis Workspace 是一款报表工具，因此不会对数据收集产生任何影响。您可以不加选择地将组件拖到项目中来查看具体效果，这不会产生任何影响。将不同的维度和量度组合拖动到工作区项目中，可查看相应的效果。

如果意外地将无效组件拖动到工作区项目，或者希望返回到上一个步骤，请按 Ctrl + Z (Windows) 或 cmd + Z (Mac) 以撤消上一个操作。此外，您还可以通过单击左上角菜单中的&#x200B;*[!UICONTROL 项目]&gt;[!UICONTROL 新建]*&#x200B;来重头开始创建。

## 故障诊断

**当我将量度拖动到上面时，显示“数据无效”。**

无效数据意味着 Adobe 无法通过报表中使用的维度和量度组合返回数据。例如，两个彼此堆叠的量度不能作为数据返回，因为无法以这种堆叠方式显示这两个量度。相反，会并排显示这两个量度。

**当我将量度拖动到上面时，看不到任何实际数据 - 只有零。**

如果您成功创建了工作区报表，但报表中没有数据，则可以检查以下几项内容：

* 仔细检查报表包，并确保报表包中已填充数据。
* 如果在报表中使用了区段，区段标准可能与所有数据不匹配。请尝试移除区段或调整区段定义。
* 检查右上角的日期范围，并确保它已设置为预期的值。
* 导航到您的网站，然后使用调试器验证正在收集的数据。

## 其他资源

* [Analysis Workspace 发行说明](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)：仔细研读该工具中引入的最新功能。
* [YouTube 上的 Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)：通过这个内容丰富的播放列表，了解如何使用 Analysis Workspace 中的大多数功能。
* 产品内提示：Analysis Workspace 的右下角不时会显示“每日提示”和一些简短视频。如果取消这些提示，您可以随时通过&#x200B;*[!UICONTROL 帮助]&gt;[!UICONTROL 提示]*&#x200B;来访问它们。
* [Analysis Workspace 社区](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace)：与同事讨论 Analysis Workspace，并就您希望在工具中看到的功能进行投票。
* 博客文章：
   * [使组织拥有更智能的分析功能](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [通过 Adobe Analytics 新增功能更容易得出独到的见解](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [使用 Analysis Workspace 最大程度提高工作效率的 5 个提示](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [快速领悟 Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [为何要使用 Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 后续步骤

您可以从多个不同角度来加深对 Analysis Workspace 的了解。以下是 Adobe 推荐掌握的一些基本知识：

### 对于希望拓展有关如何使用 Analysis Workspace 相关知识的最终用户

* [关于工作区 UI 的详细信息](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)：既然您已创建了基础报表，那么应该更加熟悉用户界面的其余部分。
* [工作区中的可视化图表](visualizations/freeform-analysis-visualizations.md)：自由格式表只是 Analysis Workspace 中可视化图表的一种类型。了解如何使用其他可视化图标，例如折线图、条形图和地理地图。
* [工作区中的维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)：了解有关什么是维度及如何在排名报表等表格中使用维度的更多信息。
* [工作区中的量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md)：了解有关什么是量度及如何在自由形式表的其他部分中使用量度的更多信息。
* [区段简介](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md)：了解什么是区段，并使用区段提取基本报告。
* [工作区中的日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)：了解相对日期和滚动日期，并在工作区项目中加以运用。
* 在工作区中共享项目：向您的同事展示您创建的精彩工作区项目。
* [（高级）工作区中的面板](c-panels/panels.md)：使用工作区中的高级功能，例如“归因”和“区段比较”。

### 对于希望提高组织中工作区质量的分析师和管理员

* [Analysis Workspace 权限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)：通过 Adobe Admin Console 向用户分配工作区权限。
* [创建解决方案设计文档](/help/implement/prepare/solution-design.md)：开始规划您的组织如何收集特定于您站点的其他维度或量度。
* [工作区中的模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)：创建模板，让您的同事可以开始根据自己的需求定制项目空间。
* [工作区管理操作](curate-share/curate.md)：创建一个限制可用组件的项目，让不太熟悉这款工具的用户也能访问这些项目
