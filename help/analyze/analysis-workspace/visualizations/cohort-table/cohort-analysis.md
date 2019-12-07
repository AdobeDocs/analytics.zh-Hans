---
keywords: Analysis Workspace
title: 什么是同类群组分析？
topic: Reports and analytics
uuid: 39a83f3a-15d1-41d7-bcdd-50c22aed8f1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 什么是同类群组分析？

*`cohort`* 是指一组在特定期限内共享相同特性的人员。例如，在您想了解如何让一个同类群组喜欢某个品牌时，同类群组分析就能派上用场。您可以轻松识别趋势中的变化，然后相应地采取回应（网上提供了有同类群组分析的解释说明，例如，[同类群组分析基础](https://en.wikipedia.org/wiki/Cohort_analysis)）。

创建队列报表后，您可以组织其组件（特定的维度、量度和区段），然后可以与其他任何人员共享这份队列报表。请参阅[策划与共享](/help/analyze/analysis-workspace/curate-share/curate.md)。

使用同类群组分析可以实现的作用（示例）：

* 启动旨在推动所需操作的促销活动。
* 在客户生命周期的恰当时间内转变营销预算。
* 识别终止试用或优惠活动的时间，以实现价值的最大化。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。
* 在引导分析报表中查看同类群组分析报表。
* 识别终止试用或优惠活动的时间，以实现价值的最大化。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。

同类群组分析适用于具有 Analysis Workspace 访问权限的所有 Analytics 客户。

[YouTube 上的同类群组分析](https://www.youtube.com/watch?v=kqOIYrvV-co&index=45&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>同类群组分析不支持计算量度。

## 同类群组分析功能

2019 年 1 月，Adobe 发布了一个功能显著增强的新版同类群组分析。该版本允许对正在构建的同类群组进行更为精细的控制。以下是其特有的增强功能：

### 维系率表

维系同类群组报表返回访客：每个数据单元格显示了同类群组中在该时间段内执行操作的访客原始数量和百分比。您最多可以包含 3 个量度和 10 个区段。

![](assets/retention-report.png)

### 流失率表

流失率同类群组与维系率表完全相反，会显示随着时间的推移，您的同类群组中已流失或从不满足回访标准的访客。您最多可以包含 3 个量度和 10 个区段。

![](assets/churn-report.png)

### 滚动计算

允许您根据前一列而不是所包含的列计算维系率或流失率。

![](assets/cohort-rolling-calculation.png)

### 延时表

衡量包含事件发生之前和之后经过的时间。此表非常适用于进行事件之前/之后分析。“已包括”列位于该表的中心，而包含事件之前和之后的时间段则分别显示在两侧。

![](assets/cohort-latency.png)

### 自定义维度同类群组

创建基于所选维度的同类群组，而不是默认的基于时间的同类群组。在 Adobe Analytics 中使用营销渠道、促销活动、产品、页面、区域或任何其他维度，可显示维系率根据这些维度值的不同有何变化。

![](assets/cohort-customizable-cohort-row.png)

有关如何设置和运行同类群组报表的说明，请转到[配置同类群组分析报表](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

