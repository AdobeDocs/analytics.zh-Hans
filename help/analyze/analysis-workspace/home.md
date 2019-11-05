---
description: 如何开始使用Adobe Analytics。
keywords: Analysis Workspace
seo-description: 如何开始使用Adobe Analytics。
seo-title: 入门指南
solution: Analytics
title: 入门指南
topic: Reports and Analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Analysis Workspace

Analysis Workspace是Adobe的旗舰工具之一，可为您的组织制定基于数据的可操作决策。 最常见的可视化形式表允许您使用维度、指标、细分和日期范围轻松创建自定义报表。

## 先决条件

[使用Adobe Experience Platform Launch将数据发送到Adobe Analytics](/help/implement/implement-with-launch/validate-publish-prod.md):使用Analysis Workspace需要一个有效的实施。 在使用该工具之前，请确保您的单位正在向Adobe发送数据。 其他实施（如DTM或旧式手动实施）也可以正常工作。

## 在Workspace中提取基本的排名报表

使用Analysis Workspace提取基本的排名报告。 排名报表显示每个维值的汇总总视图，首先显示最大值。 这些类型的报表有助于查看网站中哪些组件最有效，例如哪些页面的流量最大或哪些产品销售最多。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
3. 在顶部导航栏中，单击“工作区”。
4. 单击“创建新项目”按钮。
5. 在模态弹出窗口中，确保选中“空白项目”，然后单击“创建”。
6. 在左侧，您应当看到维度、量度、区段和日期范围的列表。 找到页面维度（橙色），并将其拖动到画布上，其中显示“将维度放在此处”。
7. 请注意，如果报表包包含数据，则可以看到显示当月最热门页面的报表。 Analysis Workspace会自动填充包含“发生次数” [量度的报](/help/components/c-variables/c-metrics/metrics-occurrences.md) 表。
8. 找到访问量度（绿色），将其拖 **动到** Occurrences **量度标题旁边** （避免将其放在该量度上方）。 如果将访问量度拖动到发生次数上方，则报表中会替换该量度。 如果将访问量度拖动到“发生次数”旁边，则两个量度将并排显示。
9. 如果要保存项目，请单击左上角 *[!UICONTROL 的菜单]&gt;[!UICONTROL 保存]* 。

## 在Workspace中提取基本趋势报告

使用Analysis Workspace提取基本趋势报告。 趋势报表显示使用选定日期范围的度量的长期视图。 这些类型的报告有助于确定一段时间内的趋势，并可用于评估业务决策的成败。 例如，您可以查看页面查看次数随时间变化的趋势报告，以了解网站重新设计是否帮助了流量的增加或减少。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
3. 在顶部导航栏中，单击“工作区”。
4. 单击“创建新项目”按钮。
5. 在模态弹出窗口中，确保选中“空白项目”，然后单击“创建”。
6. 在左侧，您应当看到维度、量度、区段和日期范围的列表。 找到“页面查看次数”维度，并将其拖动到画布上标有“在此放置度量”的小空间。 避免将其放在为尺寸保留的空间中（至少对于本练习）。
7. 请注意，如果报表包包含数据，您应当看到一个基本的页面查看次数报告在当前月份的趋势。 Analysis Workspace会自动引入“日”日期范围，以便您查看当月的页面查看趋势。
8. 在左侧的日期范围组件列表中找到周日期范围（彩色紫色）。 单击日期范围标题可展开并查看所有日期范围组件，或使用搜索栏。
9. 将周日期范围拖动到画布上的日日期范围标题上以替换它。
10. 请注意，您的趋势报表现在按周而非天进行汇总。
11. 如果要保存项目，请单击左上角 *[!UICONTROL 的菜单]&gt;[!UICONTROL 保存]* 。

## 使用工具进行试验

由于Analysis Workspace是一个报告工具，因此对数据收集没有影响。 不分青红皂白地将组件拖动到项目中以查看哪些组件有效，不会产生任何影响。 将不同的维度和指标组合拖动到工作区项目中，以查看可供您使用的内容。

如果意外地将无效组件拖动到工作区项目或希望返回一个步骤，请按ctrl+Z(Windows)或cmd+Z(Mac)以撤消上次执行的操作。 您还可以通过单击左上角菜单中的“项 *[!UICONTROL 目]” &gt;[!UICONTROL “新建]* ”，从干净的石板开始。

## 故障诊断

**当我将度量拖动到上方时，它会显示“数据无效”。**

无效数据意味着Adobe不能使用报告中使用的维度和指标组合返回数据。 例如，两个相互叠加的度量不能作为数据返回，因为无法这样显示两个度量。 相反，应并排放置度量。

**当我将一个指标拖动到上面时，我看不到任何实际数据——只有零。**

如果您成功创建了工作区报告，但没有数据，则可以检查以下几项：

* 仔细检查报表包，并确保它已填充数据。
* 如果您使用报表中的区段，则区段标准可能与任何数据不匹配。 尝试删除区段或调整区段定义。
* 检查右上角的日期范围，并确保它已设置为您期望的值。
* 导航到您的网站，然后使用调试器验证正在收集的数据。

## 其他资源

* [Analysis Workspace发行说明](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md):阅读该工具中引入的最新功能。
* [YouTube上的Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS):了解如何通过这一丰富的播放列表使用Analysis Workspace中的大多数功能。
* 产品内提示：Analysis Workspace的右下角偶尔会显示每日提示和简短视频。 如果这些提示被忽略，可随时通过“帮 *[!UICONTROL 助]&gt;提[!UICONTROL 示]* ”来访问。
* [Analysis Workspace社区](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace):与同事讨论Analysis Workspace，并就您希望在工具中看到的功能进行投票。
* 博客文章：
   * [使组织拥有更智能的分析功能](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [新的Adobe Analytics功能使功能强大的洞察更易于访问](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [使用Analysis Workspace最大化工作效率的5个提示](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [利用Analysis Workspace更快地洞察](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [为何要使用 Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 后续步骤

要加深您对Analysis Workspace的了解，有许多方向可供您参考。 以下是Adobe建议的一些基础知识：

### 对于希望扩展有关如何使用Analysis Workspace的知识的最终用户

* [工作区UI的详细信息](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md):现在您已创建了基本报告，因此对界面的其余部分更加熟悉。
* [工作区中的可视化](visualizations/freeform-analysis-visualizations.md):自由格式表只是Analysis Workspace中的一种可视化类型。 了解如何使用其他可视化，如线图、条形图和地理地图。
* [工作区中的尺寸](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md):了解更多关于维度以及如何在排名报告中使用维度的信息。
* [Workspace中的指标](/help/analyze/analysis-workspace/components/apply-create-metrics.md):进一步了解什么是指标以及如何在自由形式表的其他部分中使用它们。
* [细分简介](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md):了解什么是区段，并使用区段提取基本报告。
* [Workspace中的日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md):了解相对日期和滚动日期，并将其用于工作区项目。
* 在工作区中共享项目：向您的同事展示您创建的精彩Workspace项目。
* [（高级）工作区中的面板](c-panels/panels.md):使用Workspace中的高级功能，如归因和细分比较。

### 针对希望提高组织中工作区质量的分析师和管理员

* [Analysis Workspace权限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html):通过Adobe Admin Console向Workspace分配用户权限。
* [创建解决方案设计文档](/help/implement/prepare/solution-design.md):开始规划您的组织如何收集特定于您的站点的其他维度或指标。
* [工作区中的模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md):创建模板，让您的同事可以开始根据自己的需求定制项目空间。
* [工作区特选](curate-share/curate.md):创建一个项目以限制可用组件，使不太熟悉该工具的用户更容易访问工作区
