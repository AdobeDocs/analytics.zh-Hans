---
description: 显示有关访客访问网站页面的顺序的信息。您可以收集访客访问网站任何网页之前和之后的动向信息。
seo-description: 显示有关访客访问网站页面的顺序的信息。您可以收集访客访问网站任何网页之前和之后的动向信息。
seo-title: 路径报告
solution: Analytics
title: 路径报告
topic: Ad Hoc Analysis
uuid: 5881cb1c-6d66-49fe-ac84-70b82662 acd2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 路径报告

显示有关访客访问网站页面的顺序的信息。您可以收集访客访问网站任何网页之前和之后的动向信息。

## Paths reports {#concept_CB32E270FB9E4D929C91FDFE428CB224}

显示有关访客访问网站页面的顺序的信息。您可以收集访客访问网站任何网页之前和之后的动向信息。

路径报表包括标准的深入分析报表和可选高级分析报表，这些报表能揭示已查看页面的点击流。您可以查明完整路径、最长路径和最受欢迎的路径；通过图表对页面流量、流失和中途退出情况进行说明；显示一段时间后模式的更新和更改；分析进入和退出路径。

** [!UICONTROL Next Page Flow] ** or ** [!UICONTROL Next Site Flow]**: Displays a two-level-deep branching graphic of a selected page (or section, department, and so on), that your visitors view after moving away from the selected page. 使用此报表可分析和确定访客在查看所选页面之后采用最频繁的步骤。您可以：

* 了解查看选定页面后使用频率最高的步骤。
* 优化网站路径设计，以便将访客流量引至预期的目标页面。
* 识别访客进入了除预期目标页面之外的哪些页面。

** [!UICONTROL Next Page] ** (or next categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed after seeing a selected page. 例如，如果选择并报告整个网站的相关数据，报表会显示最受欢迎的 10 个登录页面，并在各个登录页面下方列出 5 个最受欢迎的后续页面。此数据可帮助您了解哪些内容、功能和其他数据最常促使访客浏览网站内的其他页面。。

** [!UICONTROL Previous Page Flow] ** (or other previous categories flow): Displays two levels of the most popular pages that your visitors view before the selected page. 此报表还将突出显示访客登入网站的时间。

** [!UICONTROL Previous Page] ** (or other previous categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed before seeing a selected page on your site.

** [!UICONTROL Fallout] **: Displays the visit attrition and conversion rates between each checkpoint you define. 各步骤情况按自上向下的顺序排列，其中左边是原始数字和百分数，右边是转化和流失百分比。

请参阅[流失报表](../../analyze/ad-hoc-analysis/c-reports-paths.md#concept_0ED452F3B1D04A19A59DD04D76D20347)以了解详细信息。

** [!UICONTROL Path Length] **: Shows how deep visitors browse into your site (both by percentage and by total count). 换言之，此报表指示访客退出网站前平均查看的页面数。

** [!UICONTROL Page Analysis] **: Contains a subset of reports that let you analyze the following:

* ** [!UICONTROL Page Summary / Site Category Summary] **: Tells you everything you need to know about the page report. 此报表可收集并整理单个页面的特定信息并在单个报表中显示该信息。
* ** [!UICONTROL Reloads] **: Shows the number of times individual pages were reloaded by visitors.
* ** [!UICONTROL Time Spent on Page / Site Category] **: Displays the length of time that visitors browse individual pages in your site. 逗留时间可分为 10 类：少于 15 秒、15-30 秒、30-60 秒、1-3 分钟、3-5 分钟、5-10 分钟、10-15 分钟、15-20 分钟、20-30 分钟和超过 30 分钟。
* ** [!UICONTROL Clicks to Page] **: Identifies the number of clicks visitors used to access each page in your site. 测量页面深度的方法是计算在该页面之前查看的页面数量。

** [!UICONTROL Entries &amp; Exits] **: The [!UICONTROL Entry Page] report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visitors. 您可查看：

* ** [!UICONTROL Entry Pages] ** (or sections): Displays, by percentage and by total visits, which pages on your site are the first pages seen by a new visitor. 您可以使用此报表来确定哪些网页的登录次数最多，而且可优化网站上的主要登录点并提升关键消息的登录流量。
* ** [!UICONTROL Original Entry Pages] **: Shows the first page viewed for first-time visitors to your site. 每个用户仅计数一次，除非他们删除其 cookie 或没有通过 cookie 受到跟踪。
* ** [!UICONTROL Single Page Visits] **: Shows pages that are most often both the entry and exit pages for visitor browsing sessions.
* ** [!UICONTROL Exit Pages] **: Displays, by percentage and by total visits, the pages on your site that were the last pages visitors viewed before leaving your site.

## 流失报表 {#concept_0ED452F3B1D04A19A59DD04D76D20347}

[!UICONTROL 流失报表]可显示访客在何处离开（流失）并继续浏览（途经）一系列预先指定的页面。它可显示每个步骤之间的转化和流失比率。例如，您可以跟踪购买期间访客的流失点数。应选择开始点和结束点，然后添加中间点以创建网站导航路径。

<!-- 

c_reports_fallout.xml

 -->

您可以对访问或访客级别的流失数据进行分析。您也可以查看以图表形式显示的趋势路径，了解特定时段内的流失情况。您可以将一个页面或多组页面设置为报表检查点，也可以按任意组合或顺序添加任何维度或量度。在 Marketing Reports &amp; Analytics 中配置的类别也可用作此报表中的检查点。

此报表可用于分析：

* 网站上特定过程的转化率（例如购买或注册过程）。
* 一般、更宽范围的流量：显示在查看主页的访客中，有多少人继续进行搜索及有多少人最终查看特定项目。
* 网站上事件之间的关联。显示查看隐私政策后继续购买产品的访客百分比。

## 运行流失报表 {#task_3594E8BE55964C1C8B0BEC8DEABF82D3}

运行[!UICONTROL 流失报表]的步骤。

<!-- 

t_fallout.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL New Report]** &gt; **[!UICONTROL Fallout.]**

   Other Fallout reports are found in **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]**.

1. （可选）如果要按特定区段过滤数据，请将区段拖到“[!UICONTROL 在此放置区段]”字段中。
1. 将任意维度项目拖到“[!UICONTROL 在此放置事件或维度项目]”字段中。
1. Click **[!UICONTROL Show Fallout At]**Visit or Visitor level, depending on whether you want to view fallout at the visit level, or across visitor sessions.
1. 向报表中添加维度项目，例如页面。

## 为流失报表分配页面 {#task_B386289703494FA7B5A40FF9F97CB537}

为流失报表分配页面的步骤。

<!-- 

t_fallout_assign_pages.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Pages Fallout]**.
1. 从“维度”窗格中，找到要添加的页面，然后将其拖到[!UICONTROL 在此放置事件或维度]字段。

## 流失报表 - 字段说明 {#reference_74255CC8D6134F349FEBFEC72934C866}

[!UICONTROL 流失]报表的字段描述。

<!-- 

r_dsc_fallout.xml

 -->

| 字段 | 说明 |
|--- |--- |
| 在访问和访客级别显示流失数据 | 用于在“访问”和“访客”之间切换以分析访客路径。这些设置可以帮助您了解不同访问中的访客级别的访客参与情况。已启用网站分析、流量和流失报表以进行访客路径分析。更改此设置会重新运行报表，将数据限制为所选内容。 |
| 总成功率 | 成功的总指标。此值表示路径上一检查点中的值。 |
| 总成功率 % | 到达每个检查点的访客百分比的累计总数。 |
| 检查点 % | 检查点之间的成功率百分比。（不累计。） |
| 包括所有访问 | 将所有访问添加为初始检查点。 |
| 流失 | 用于查看落在特定检查点路径之外的访客所查看的页面。 |
| 途经 | 用于查看特定检查点路径的下一步中所查看的页面。 |
