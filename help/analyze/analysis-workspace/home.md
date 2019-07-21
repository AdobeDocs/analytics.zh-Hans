---
description: 如何开始使用Adobe Analytics。
keywords: Analysis Workspace
seo-description: 如何开始使用Adobe Analytics。
seo-title: 入门指南
solution: Analytics
title: 入门指南
topic: Reports & Analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: a0158b98089c044091f61796d782604865aa4eba

---


# Analysis Workspace

Analysis Workspace是Adobe的旗舰工具之一，可为您的组织制定切实可行的基于数据的决策。最常见的可视化可视化是自由表格，允许您使用维度、指标、细分和日期范围轻松创建自定义报表。

## 先决条件

[使用Adobe Experience Platform Launch将数据发送到Adobe Analytics](../../implement/implement-with-launch/validate-publish-prod.md)：使用Analysis Workspace需要一个工作实施。请确保您的组织在使用该工具之前向Adobe发送数据。其他实现(如DTM或传统手动实现)也可以正常工作。

## 在Workspace中提取基本的排名报告

使用Analysis Workspace提取基本的排名报告。排名报告显示每个维度值的汇总总视图，首先显示最大值。这些类型的报告非常有用，可用于查看站点的哪些组件最有效，例如哪些页面获得最多流量或哪些产品销售最多。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. 单击右上角的方形图标，然后单击彩色的Analytics徽标。
3. 在顶部导航栏中，单击工作区。
4. 单击“创建新项目”按钮。
5. 在模态弹出窗口中，确保选中“空白项目”，然后单击“创建”。
6. 您应当在左侧看到维度、指标、细分和日期范围列表。找到“页面”尺寸(彩色橙色)，然后将其拖到画布上，在画布上将其表示为“在此处放置尺寸”。
7. 请注意，如果报表包有数据，则会显示一份显示本月顶部页面的报告。Analysis Workspace automatically populated the report with the [Occurrences](../../components/c-variables/c-metrics/metrics-occurrences.md) metric.
8. Locate the Visits metric (colored green), and drag it either **over** or **next to** the Occurrences metric header (avoid placing it above the metric). 如果将“访问”量度拖动到“发生次数”上方，则会在报告中替换该量度。如果您将“访问”量度拖动到“发生次数”旁边，两个量度将并排显示。
9. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## 在Workspace中提取基本趋势报告

使用Analysis Workspace提取基本趋势报告。趋势报告显示使用选定日期范围的指标的实时视图。这些类型的报告可用于确定随着时间的推移趋势，并可用于评估业务决策的成功或失败。例如，您可以查看一段随时间推移的页面查看报告，以了解站点重新设计是否有助于提高或减少流量。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. 单击右上角的方形图标，然后单击彩色的Analytics徽标。
3. 在顶部导航栏中，单击工作区。
4. 单击“创建新项目”按钮。
5. 在模态弹出窗口中，确保选中“空白项目”，然后单击“创建”。
6. 您应当在左侧看到维度、指标、细分和日期范围列表。找到页面查看维度，并将其拖动到画布上标记为“在此处放置量度”的小空间。避免将其放入保留尺寸的空间(至少用于此练习)。
7. 请注意，如果报表包有数据，则您应当看到当月的基本页面查看报告趋势。Analysis Workspace会自动引入“天”日期范围，因此您可以查看当月页面查看的趋势。
8. 在左侧的日期范围组件列表中找到周日期范围(彩色紫色)。单击日期范围标题以展开和查看所有日期范围组件，或使用搜索栏。
9. 将周日期范围拖动到画布上的日期日期范围标题上方以替换它。
10. 请注意，趋势报告现在按周汇总，而不是每天汇总。
11. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## 使用工具进行试验

由于Analysis Workspace是一种报表工具，因此它对数据收集没有影响。不会影响将组件拖入项目以查看有效内容。将不同的维度和计量指标组合拖入工作区项目，以了解可供您使用的内容。

如果意外将无效组件拖动到工作区项目或希望返回一个步骤，按Ctrl+ Z(Windows)或cmd+ Z(Mac)可撤消上次执行的操作。You can also start with a clean slate by clicking *[!UICONTROL Project]&gt;[!UICONTROL New]* in the upper left menu.

## 故障诊断

**在我拖动指标时，它表示“数据无效”。**

无效数据意味着Adobe无法使用报告中使用的维度和量度组合返回数据。例如，堆叠在彼此之上的两个指标不能作为数据返回，因为没有办法以这种方式显示两个指标。相反，请并排放置指标。

**在我拖动指标时，我看不到任何实际数据-只需零。**

如果您成功创建了工作区报告但没有数据，您可以检查以下几项：

* 双击报表包，确保它包含数据填充。
* 如果您使用报表中的区段，则区段条件可能与任何数据不符。尝试删除区段或调整区段定义。
* 检查右上角的日期范围，确保将其设置为您期望的值。
* 导航到您的网站并使用调试器验证正在收集的数据。

## 其他资源

* [Analysis Workspace发行说明](../../analyze/analysis-workspace/new-features-in-analysis-workspace.md)：阅读介绍的最新功能。
* [YouTube上的Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)：通过这个广泛的播放列表了解如何使用Analysis Workspace中的大多数功能。
* 产品内提示：每天的提示以及简短的视频偶尔会出现在Analysis Workspace的右下角。If these tips are dismissed, they can be reached through *[!UICONTROL Help]&gt;[!UICONTROL Tips]* at any time.
* [Analysis Workspace社区](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace)：与同行用户讨论Analysis Workspace，并投票您希望在工具中看到的功能。
* 博客帖子：
   * [使组织拥有更智能的分析功能](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [新的Adobe Analytics功能使强大的洞察更易于访问](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [使用Analysis Workspace最大限度提高工作效率的提示](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [利用Analysis Workspace更快地洞察](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [为何要使用 Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 后续步骤

要加深对Analysis Workspace的了解，有很多方向。下面是Adobe建议的一些基本知识：

### 适用于希望扩展如何使用Analysis Workspace的最终用户

* [工作区UI的详细信息](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)：既然您已经创建了一份基本报告，请更加熟悉界面的其余部分。
* [Workspace中的可视化](visualizations/freeform-analysis-visualizations.md)：自由表只是Analysis Workspace中的一种可视化形式。了解如何使用其他可视化功能，如折线图、条形图和地理地图。
* [Workspace中的维度](../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)：进一步了解哪些维度以及如何使用这些维度不仅仅是排名报告。
* [Workspace中的指标](../../analyze/analysis-workspace/components/apply-create-metrics.md)：了解有关哪些指标以及如何在自由表单的其他部分使用这些指标的更多信息。
* [细分介绍](../../analyze/analysis-workspace/components/t-freeform-project-segment.md)：了解哪些细分以及使用区段提取基本报表。
* [Workspace中的日期范围](../../analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)：了解相对和滚动日期，并将其用于工作区项目。
* 在Workspace中共享项目：向您的同事展示您创建的精彩工作区项目。
* [(高级)工作区中的面板](c-panels/panels.md)：使用Workspace中的高级功能，如归因和细分比较。

### 对于分析师和admin而言，希望提高其组织工作区的质量

* [Analysis Workspace权限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)：通过Adobe Admin Console为工作区分配权限。
* [创建解决方案设计文档](../../implement/prepare/solution-design.md)：开始规划组织如何收集特定于您网站的其他维度或指标。
* [Workspace中的模板](../../analyze/analysis-workspace/build-workspace-project/starter-projects.md)：创建模板，让您的同事可以从量身定制的项目空间开始。
* [工作区策展](curate-share/curate.md)：创建一个限制可用组件的项目，使那些熟悉工具的人员更容易访问工作区