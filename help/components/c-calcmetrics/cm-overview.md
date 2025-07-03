---
description: 计算量度和高级计算量度是指您可以从现有量度创建的自定义量度。
keywords: 计算量度；高级计算量度
title: 计算量度和高级计算量度
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: ht
source-wordcount: '288'
ht-degree: 100%

---

# 计算量度概述

您可以基于现有量度创建的计算量度和自定义量度。

计算量度提供了一种高度灵活的方式，可用于生成、管理和组织量度。通过使用这些计算量度，营销人员、产品经理和分析人员不必更改 [!DNL Analytics] 实施，即可提出有关数据的问题。

每个 [!DNL Analytics] 套件中均提供计算量度功能，但 Adobe Analytics Foundation Pack for Experience Cloud 仅限于使用基本的计算量度，包括[格式类型（小数、时间、百分比、货币）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)和[归因方式更改（默认、线性、参与等）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)、[量度类型（标准、总计）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)和[基本运算符](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#operators)（加、减、乘、除）。


有关详细信息，请参阅 [Adobe Analytics 产品说明](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-analytics.html)。

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/c-calcmetrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* 在 [!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 异常检测]和[!UICONTROL 贡献度分析]中[创建量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md)。
* [创建在报表运行时派生的分段量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md)，而不必更改实施。例如，您可以为&#x200B;*新访客*&#x200B;创建一个量度，其中包含首次进行会话的人员计数。

* 在报表包之间[共享量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)。这表示所有新创建的量度都适用于同一登录公司中的所有报告包。

* [整合统计函数](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md)以帮助您更好地描述数据。例如，您可以计算报告中的项数，或为每一项添加标准差数字。

## 限制

某些 [!DNL Analytics] 功能不允许使用计算量度：

* Analysis Workspace 中的流失
* [!UICONTROL Analysis Workspace 中的队列分析]
* [!UICONTROL Data Warehouse]
* [!UICONTROL 区段]
* [!DNL Analytics] 用于 [!DNL Target]


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [计算量度](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [区段中的分段计算量度](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[创建量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md)
>>[生成指标](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)
>>[使用函数](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-using-functions.md)
>
