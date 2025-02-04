---
title: 同类群组分析是什么及其如何工作？
description: 用同类群组分析更深入地挖掘您受众周围的数据并细分为相关的各组。了解 Analysis Workspace 中的同类群组分析。
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 33%

---

# 同类群组表概述 {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="同类群组表"
>abstract="创建可视化同类群组，根据事件的完成情况对用户进行分组，并分析持续的参与度和一段时间内的流失率。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="同类群组表"
>abstract="根据事件的完成情况分组用户，然后分析这些用户在一段时间内的持续参与和流失程度。<br/><br/>**参数&#x200B;**<br/>**纳入标准**：用于定义您的初始访客同类群组的组件。<br/>**回访标准**：用于确定访客是否已回访的组件。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的同类群组表。_<br/>_查看本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本的[同类群组表](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis)。_

>[!ENDSHADEBOX]



*同类群组*&#x200B;是在指定时间段内共享相同特征的一组人员。 例如，在您想了解如何让一个同类群组喜欢某个品牌时，![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同类群组表]**&#x200B;可视化图表很有用。 您可以轻松识别趋势中的变化，然后相应地采取回应。（网上提供了有关[!UICONTROL 同类群组分析]的解释说明，例如[同类群组分析基础](https://zh.wikipedia.org/wiki/Cohort_analysis)。）

创建同类群组报表后，您可以组织其组件（特定的维度、量度和过滤器），然后可以与其他任何人员共享这份同类群组报表。请参阅[策划和共享](/help/analyze/analysis-workspace/curate-share/curate.md)。

使用[!UICONTROL 同类群组表]可以执行的操作示例：

* 启动旨在推动所需操作的促销活动。
* 在客户生命周期的恰当时间内转变营销预算。
* 识别终止试用或优惠活动的时间，以实现价值最大化。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。

[!UICONTROL 同类群组表]适用于具有[!UICONTROL Analysis Workspace]访问权限的所有Customer Journey Analytics客户。


>[!BEGINSHADEBOX]

观看演示视频，请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[Analysis Workspace中的同类群组分析](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL 同类群组分析]不支持不可过滤的量度（包括计算量度）、非整数量度（如收入）或发生次数。 只有可在筛选器中使用的量度才能在[!UICONTROL 同类群组分析]中使用，并且这些量度一次只能递增1。

Customer Journey Analytics中的同类群组表支持基于双精度指标（或任何基于数字的指标）。 例如，Purchase.Value(a double)可用作包含/返回量度。 此外，通过Analytics Source Connector传递到Adobe Experience Platform的所有量度也是双精度的。

## 同类群组表功能

以下部分介绍了同类群组分析功能，这些功能允许您对正在构建的同类群组进行精细控制。

有关创建同类群组并运行[!UICONTROL 同类群组分析]报表的更多详细信息，请参阅[配置同类群组表](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

### [!UICONTROL 保留]表

[!UICONTROL 维系]同类群组表返回人员：每个数据单元格显示了同类群组中在该时间段内执行操作的原始人数和百分比。 您最多可以包含 3 个量度和 10 个过滤器。

![显示同类群组中人员的单位和百分比的演绎版同类群组报告。](assets/retention-report.png)

### [!UICONTROL 流失]表

[!UICONTROL 流失率]同类群组表与维系率表完全相反，会显示随着时间的推移，您的同类群组中已流失或从不满足回访标准的人员。 您最多可以包含 3 个量度和 10 个过滤器。

![显示不符合同类群组回访标准的单位和人员百分比的客户流失表。](assets/churn-report.png)

### [!UICONTROL 滚动计算]

您可以根据前一列而不是所包含的列计算维系率或流失率，该列称为滚动计算。

![显示基于上一列数据的计算的同类群组保留报表。](assets/retention-report-rolling.png)

### [!UICONTROL 延迟]表

延时表衡量包含事件发生之前和之后经过的时间。 测量滞后时间是进行事前和事后分析的绝佳工具。 **[!UICONTROL 已包括]**&#x200B;列位于该表的中心，而包含事件之前和之后的时间段则分别显示在两侧。

![显示事件前后经过时间的同类群组报告。](assets/retention-report-latency.png)

### [!UICONTROL 自定义维度]同类群组

您可以创建基于选定维度的同类群组，而不是基于时间的同类群组（默认设置）。 使用维度（如[!UICONTROL 城市地域]、[!UICONTROL 营销渠道]、[!UICONTROL 促销活动]、[!UICONTROL 产品]、[!UICONTROL 页面]、[!UICONTROL 区域]或任何其他维度）来显示维系率的变化情况。 基于这些维度的不同值。

![显示自定义报告的同类群组报告具有所选维度，而不是默认的基于时间的同类群组。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[配置同类群组表](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>



<!--
A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and segments), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer, in order to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort Analysis] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://video.tv.adobe.com/v/25965?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-segmentable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. 
>
>Only metrics that can be used in segments can be used in [!UICONTROL Cohort Analysis], and they can only be incremented by >1 at a time. 

## Cohort Analysis capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort Analysis report](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention] Table

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 segments.

![](assets/retention-report.png)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://video.tv.adobe.com/v/25962?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://video.tv.adobe.com/v/25966?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


### [!UICONTROL Rolling Calculation]

Lets you calculate retention or churn based on the previous column, not the included column.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Table

Measures the time that has elapsed before and after the inclusion event occurred. This is an excellent tool for pre/post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Create cohorts based on a selected dimension, and not time-based cohorts, which are the default. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

-->
