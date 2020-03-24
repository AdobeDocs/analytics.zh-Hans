---
keywords: Analysis Workspace
title: 什么是同类群组分析？
topic: Reports and analytics
uuid: 39a83f3a-15d1-41d7-bcdd-50c22aed8f1c
translation-type: tm+mt
source-git-commit: 99232c5bce94cfc55b9f01080555cb8e545442e9

---


# 什么是同类群组分析？

*`cohort`* 是指一组在特定期限内共享相同特性的人员。例如，在您想了解如何让一个同类群组喜欢某个品牌时，同类群组分析就能派上用场。您可以轻松识别趋势中的变化，然后相应地采取回应（网上提供了有同类群组分析的解释说明，例如，[同类群组分析基础](https://en.wikipedia.org/wiki/Cohort_analysis)）。

创建同期群报表后，您可以管理其组件（特定维度、指标和细分），然后与任何人共享同期群报表。 See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

使用同类群组分析可以实现的作用（示例）：

* 启动旨在刺激所需操作的营销活动。
* 在客户生命周期中的恰当时间调整营销预算。
* 识别何时结束试用或优惠，以实现最大价值。
* 在价格、升级途径等方面获得A/B测试的想法。
* 在引导分析报表中查看同类群组分析报表。

对Analysis Workspace具有访问权限的所有Analytics客户都可以使用同期群分析。

[YouTube 上的同类群组分析](https://www.youtube.com/watch?v=kqOIYrvV-co&index=45&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>同类群组分析不支持计算量度。

## 同类群组分析功能

2019 年 1 月，Adobe 发布了一个功能显著增强的新版同类群组分析。它允许对您正在构建的群组进行更精细的控制。 以下是功能增强：

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

测量包含事件发生前后经过的时间。 这是用于前／后分析的极好工具。 “已包含”列位于表的中心，并且包含事件前后的时间段在两侧显示。

![](assets/cohort-latency.png)

### 自定义维度同类群组

根据选定的维度（而非默认的基于时间的同期）创建同期群。 在Adobe Analytics中使用营销渠道、营销活动、产品、页面、区域或任何其他维度来显示保留率如何根据这些维度的不同值而变化。

![](assets/cohort-customizable-cohort-row.png)

有关如何设置和运行同期群报告的说明，请转到配置 [同期群分析报告](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

