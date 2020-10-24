---
title: 每位访客逗留时间（秒）
description: null
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '153'
ht-degree: 100%

---


# 每位访客逗留时间（秒）

“每位访客逗留时间（秒）”量度显示访客在访客整个生命周期中与给定维度项目交互的平均时间。

此量度因其处理架构不同而在 Data Warehouse 中不可用。

## 如何计算此量度

此量度使用公式 [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md)。

## 百分比高于 100%

此量度通常包含高于 100% 的百分比。分母是整个维度的每位访客逗留时间，分子是维度项目的每位访客逗留时间。如果整个维度的每位访客逗留时间少于给定维度项目的每位访客逗留时间，您将看到高于 100% 的百分比。按此量度对排名报表进行排序，会显示网站平均深度的异常值，该值通常没什么价值。Adobe 建议在排名报表中按其他量度（例如[访问次数](visits.md)）来排序。

有关逗留时间的更多常规信息，请参阅[逗留时间概述](time-spent.md)。
