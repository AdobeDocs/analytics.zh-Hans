---
title: 每位访客逗留时间（秒）
description: null
translation-type: tm+mt
source-git-commit: 5282ad3f6fdd2853979cbfb2707cc07a698f63a7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 6%

---


# 每位访客逗留时间（秒）

“每访客花费的时间（秒）”度量显示访客在访客整个生命周期中与给定维度值交互的平均时间。

由于数据仓库的处理架构不同，此度量在数据仓库中不可用。

## 如何计算此度量

此度量使用公式 [`Total seconds spent`](total-seconds-spent.md)`divided by`[`Unique visitors`](unique-visitors.md)。

## 百分比超过100%

此指标通常包含100%以上的百分比。 分母是整个维的每个访客所花费的时间，分子是维值的每个访客所花费的时间。 如果整个维度的每个访客所用时间低于给定维度值的每个访客所用时间，您将看到100%以上的百分比。 按此指标对排名报告进行排序时，会显示每个访客值的异常花费时间，这通常不值钱。 Adobe建议在排名报告中按其他指标 [(如](visits.md)“访问”)排序。

有关 [停留时间的更多](time-spent.md) 、一般信息，请参阅停留时间概述。
