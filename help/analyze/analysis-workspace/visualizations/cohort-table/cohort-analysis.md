---
title: 同类群组分析是什么及其如何工作？
description: 用同类群组分析更深入地挖掘您受众周围的数据并细分为相关的各组。了解 Analysis Workspace 中的同类群组分析。
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 86%

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

*`cohort`* 是指一组在特定期限内共享相同特性的人员。例如，在您想了解如何让一个同类群组喜欢某个品牌时，[!UICONTROL 同类群组分析]就能派上用场。您可以轻松识别趋势中的变化，然后相应地采取回应。（网上提供了有关[!UICONTROL 同类群组分析]的解释说明，例如[同类群组分析基础](https://zh.wikipedia.org/wiki/Cohort_analysis)。）

创建队列报表后，您可以组织其组件（特定的维度、指标和区段），然后可以与其他任何人员共享这份队列报表。请参阅[策划和共享](/help/analyze/analysis-workspace/curate-share/curate.md)。

使用[!UICONTROL 同类群组分析]可以实现的作用（示例）：

* 启动旨在推动所需操作的促销活动。
* 在客户生命周期的恰当时间内转变营销预算。
* 识别终止试用或产品建议活动的时间，以实现价值的最大化。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。

[!UICONTROL 同类群组分析]适用于具有 [!UICONTROL Analysis Workspace] 访问权限的所有 Adobe Analytics 客户。

关于 Analysis Workspace 中同类群组表的视频：

>[!VIDEO](https://video.tv.adobe.com/v/25965/?quality=12)

>[!IMPORTANT]
>
>[!UICONTROL 同类群组分析]不支持不可分段的量度（包括计算量度）、非整数量度（如收入）以及“发生次数”量度。
>
>只有可以在区段中使用的量度才能在[!UICONTROL 同类群组分析]中使用，并且它们一次只能递增 1。

## 同类群组分析功能

以下部分介绍了同类群组分析功能，这些功能允许您对正在构建的同类群组进行精细控制。

有关创建同类群组并运行[!UICONTROL 同类群组分析]报表的更多详细信息，请参阅[配置同类群组分析报表](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

### [!UICONTROL 维系率表]

[!UICONTROL 维系]同类群组报表返回访客：每个数据单元格显示了同类群组中在该时间段内执行操作的访客原始数量和百分比。您最多可以包含 3 个指标和 10 个区段。

![](assets/retention-report.png)

以下是一段关于计算滚动留存率的视频：

>[!VIDEO](https://video.tv.adobe.com/v/25962/?quality=12)

### [!UICONTROL 流失率表]

[!UICONTROL 流失率]同类群组与维系率表完全相反，会显示随着时间的推移，您的同类群组中已流失或从不满足回访标准的访客。您最多可以包含 3 个指标和 10 个区段。

![](assets/churn-report.png)

以下是一段关于流失分析的视频：

>[!VIDEO](https://video.tv.adobe.com/v/25966/?quality=12)

### [!UICONTROL 滚动计算]

允许您根据前一列而不是所包含的列计算维系率或流失率。

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL 延时]表

衡量包含事件发生之前和之后经过的时间。此表非常适用于进行事件之前/之后分析。**[!UICONTROL 已包括]**&#x200B;列位于该表的中心，而包含事件之前和之后的时间段则分别显示在两侧。

![](assets/cohort-latency.png)

### [!UICONTROL 自定义维度]同类群组

创建基于所选维度的同类群组，而不是默认的基于时间的同类群组。在 Adobe Analytics 中使用[!UICONTROL 营销渠道]、[!UICONTROL 促销活动]、[!UICONTROL 产品]、[!UICONTROL 页面]、[!UICONTROL 区域]或任何其他维度，可显示维系率根据这些维度值的不同有何变化。

![](assets/cohort-customizable-cohort-row.png)
