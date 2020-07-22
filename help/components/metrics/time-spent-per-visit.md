---
title: 每次访问逗留时间
description: 维项目的每次访问所花费的时间。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 3%

---


# 每次访问逗留时间（秒）

*此帮助页面描述“每次访问所花时间”如何作为度量。 有关详[细信息，请参阅](../dimensions/time-spent-per-visit.md)“每次访问所花时间”维。*

“每次访问所用时间（秒）”度量显示访客在每次访问期间与给定维度项目交互的平均时间。

此度量因处理架构不同而在Data warehouse中不可用。

## 如何计算此度量

此度量使用公 [`Total seconds spent`](total-seconds-spent.md) 式( `divided by`[`Visits`](visits.md)`minus`[`Bounces`](bounces.md))。

## 与网站平均停留时间的比较

此指标和 [网站平均停留时间相似](average-time-on-site.md) ，但有几个关键区别。 这两个指标都使用“所用总秒数”作为分子。 但是，“站点平均时间”使用包含维项的序列作为其分母。 每次访问所花费的时间使用访问计数作为分母。

因此，这些指标在访问级别产生类似的结果，但在点击级别则不同。

## 百分比超过100%

此指标通常包含100%以上的百分比。 分母是整个维的每次访问所花费的时间，分子是维项的每次访问所花费的时间。 如果整个维度的每次访问时间低于给定维度项目的每次访问时间，您将看到100%以上的百分比。 按此指标对排名报告进行排序，可显示每次访问值的异常花费时间，这通常不值钱。 Adobe建议在排名报告中按其他指标 [(如](visits.md)“访问”)排序。

有关 [停留时间的更多](time-spent.md) 、一般信息，请参阅停留时间概述。
