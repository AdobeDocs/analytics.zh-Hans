---
title: 同类群组分析是什么及其如何工作？
description: 用同类群组分析更深入地挖掘您受众周围的数据并细分为相关的各组。了解 Analysis Workspace 中的同类群组分析。
feature: Visualizations
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 244f839235f55b7f8873864ced3d5adc2394b631
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 98%

---

# 了解 Adobe Analytics 中的[!UICONTROL 同类群组分析]

*`cohort`* 是指一组在特定期限内共享相同特性的人员。例如，在您想了解如何让一个同类群组喜欢某个品牌时，[!UICONTROL 同类群组分析]就能派上用场。您可以轻松识别趋势中的变化，然后相应地采取回应。（网上提供了有关[!UICONTROL 同类群组分析]的解释说明，例如[同类群组分析基础](https://en.wikipedia.org/wiki/Cohort_analysis)。）

创建队列报表后，您可以组织其组件（特定的维度、指标和区段），然后可以与其他任何人员共享这份队列报表。请参阅[策划和共享](/help/analyze/analysis-workspace/curate-share/curate.md)。

使用[!UICONTROL 同类群组分析]可以实现的作用（示例）：

* 启动旨在推动所需操作的促销活动。
* 在客户生命周期的恰当时间内转变营销预算。
* 识别终止试用或优惠活动的时间，以实现价值的最大化。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。
* 在引导分析报表中查看[!UICONTROL 同类群组分析]报表。

[!UICONTROL 同类群组分析]适用于具有 [!UICONTROL Analysis Workspace] 访问权限的所有 Adobe Analytics 客户。

[同类群组分析视频教程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html?lang=zh-Hans)（4 分 36 秒）

>[!IMPORTANT]
>
>[!UICONTROL 同类群组分析]
>
>不支持不可分段的指标（包括计算指标）、非整数指标（如收入）以及“发生次数”指标。只有可在区段中使用的指标才能用于
>[!UICONTROL 同类群组分析]，并且这些指标一次只能增加 1 个单位。

## 同类群组分析功能

以下功能允许您对正在构建的同类群组进行精细控制：

### [!UICONTROL 维系率表]

[!UICONTROL 维系]同类群组报表返回访客：每个数据单元格显示了同类群组中在该时间段内执行操作的访客原始数量和百分比。您最多可以包含 3 个指标和 10 个区段。

![](assets/retention-report.png)

以下是有关计算滚动维系率的视频：

>[!VIDEO](https://video.tv.adobe.com/v/25962/?quality=12)

### [!UICONTROL 流失率表]

[!UICONTROL 流失率]同类群组与维系率表完全相反，会显示随着时间的推移，您的同类群组中已流失或从不满足回访标准的访客。您最多可以包含 3 个指标和 10 个区段。

![](assets/churn-report.png)

### [!UICONTROL 滚动计算]

允许您根据前一列而不是所包含的列计算维系率或流失率。

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL 延时]表

衡量包含事件发生之前和之后经过的时间。此表非常适用于进行事件之前/之后分析。**[!UICONTROL 已包括]**&#x200B;列位于该表的中心，而包含事件之前和之后的时间段则分别显示在两侧。

![](assets/cohort-latency.png)

### [!UICONTROL 自定义维度]同类群组

创建基于所选维度的同类群组，而不是默认的基于时间的同类群组。在 Adobe Analytics 中使用[!UICONTROL 营销渠道]、[!UICONTROL 促销活动]、[!UICONTROL 产品]、[!UICONTROL 页面]、[!UICONTROL 区域]或任何其他维度，可显示维系率根据这些维度值的不同有何变化。

![](assets/cohort-customizable-cohort-row.png)

有关如何设置和运行同类群组报表的说明，请转至[配置同类群组分析报表](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
