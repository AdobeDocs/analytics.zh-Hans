---
title: 每次访问逗留时间（指标）
description: 维度项目的每次访问逗留时间。
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: ht
source-wordcount: '260'
ht-degree: 100%

---

# 每次访问逗留时间（秒）

*此帮助页面介绍“每次访问逗留时间”如何作为维度使用。有关更多信息，请参阅[每次访问逗留时间](../dimensions/time-spent-per-visit.md)维度。*

“每次访问逗留时间（秒）”指标显示访客在每次访问期间与给定维度项目交互的平均时间。

此指标因其处理架构不同而在 Data Warehouse 中不可用。

## 如何计算此量度

此指标使用公式 [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`。

## 与网站平均逗留时间相比较

此指标和[网站平均逗留时间](average-time-on-site.md)相似，但有几个主要区别。两个指标都使用“所用总秒数”作为分子。但是，“网站平均逗留时间”使用包含维度项作为分母的序列。每次访问逗留时间使用访问计数作为其分母。

因此，这些指标可能会在访问级别产生相似的结果，但在点击级别则将产生不同的结果。

## 百分比高于 100%

此指标通常包含高于 100% 的百分比。分母是整个维度的每次访问逗留时间，分子是维度项目的每次访问逗留时间。如果整个维度的每次访问逗留时间少于给定维度项目的每次访问逗留时间，您将看到高于 100% 的百分比。按此指标对排名报表进行排序，可显示每次访问逗留时间的异常值，此值通常没什么价值。Adobe 建议在排名报表中按其他指标（例如[访问次数](visits.md)）来排序。

有关逗留时间的更多常规信息，请参阅[逗留时间概述](time-spent.md)。
