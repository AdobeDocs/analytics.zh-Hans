---
description: 计算量度和高级计算量度是指您可以从现有量度创建的自定义量度。
keywords: 计算量度；高级计算量度
title: 计算量度和高级计算量度
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 9714863374052e257e1d6349c442fc74182a0a2f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 计算量度和高级计算量度

计算量度和高级计算量度是指您可以从现有量度创建的自定义量度。

我们的计算量度工具提供了一种高度灵活的方式，可用于生成、管理和组织量度。通过使用这些工具，营销人员、产品经理和分析人员不必更改 [!DNL Analytics] 实施，即可提出有关数据的问题。每个 [!DNL Analytics] 包中可用的自定义量度包括：

* Adobe [!DNL Analytics] Foundation：计算量度
* [Adobe Analytics Select](https://www.adobe.com/cn/data-analytics-cloud/analytics/select.html)：计算量度 + 高级计算量度
* [Adobe Analytics Prime](https://www.adobe.com/cn/data-analytics-cloud/analytics/prime.html)：计算量度 + 高级计算量度
* [Adobe Analytics Ultimate](https://www.adobe.com/cn/data-analytics-cloud/analytics/ultimate.html)：计算量度 + 高级计算量度

以下是计算量度和高级计算量度功能的比较：

| Builder 选项 | 计算量度 | 高级计算量度 |
|---|---|---|
| [格式类型（小数、时间、百分比、货币）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | 是 | 是 |
| [归因更改（默认、线性、参与率等）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| [量度类型（标准、总数）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| 基本运算符（加、减、乘、除） | 是 | 是 |
| [应用区段](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | 否 | 是 |
| [基本函数（计数、绝对值、平均值等）](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | 否 | 是 |
| [高级函数（回归、if/then、t 分数等）](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | 否 | 是 |

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* 在 [!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 异常检测]和 [!UICONTROL 贡献度分析]中创建量度。
* 创建在报告运行时派生的分段量度，而不必更改实施。这些量度可以在历史记录中查看，因为它们是基于区段的。

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [计算量度](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]

* 在报告包之间共享量度。这表示所有新创建的量度都适用于同一登录公司中的所有报告包。
* （仅限高级计算量度）量度上的区段。例如，您可以为“新访客”创建一个首次进行会话的人员计数的量度。

* （仅限高级计算量度）包含统计函数，以帮助您更好地描述数据。例如，您可以计算报告中的项数，或为每一项添加标准差数字。


## 限制

某些 [!DNL Analytics] 功能让您可以使用事件，而不是计算量度：

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