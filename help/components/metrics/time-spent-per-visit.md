---
title: 每次访问逗留时间（指标）
description: 维度项目的每次访问逗留时间。
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
TQID: https://experienceleague.adobe.com/X1RtHTTmu0VIblFC3jANE7d6bIbtm4W5OvqFZDp8bLE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 263
ht-degree: 90%

---

# 每次访问逗留时间（秒）

*此帮助页面介绍“每次访问逗留时间”如何作为维度使用。 有关更多信息，请参阅[每次访问逗留时间](../dimensions/time-spent-per-visit.md)维度。*

“每次访问逗留时间（秒）”量度[量度](overview.md)显示访客在每次访问期间与给定维度项目交互的平均时间。

此指标因其处理架构不同而在 Data Warehouse 中不可用。

## 如何计算此指标

此指标使用公式 [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`。

## 与网站平均逗留时间相比较

此指标和[网站平均逗留时间](average-time-on-site.md)相似，但有几个主要区别。 两个指标都使用“所用总秒数”作为分子。 但是，“网站平均逗留时间”使用包含维度项作为分母的序列。 每次访问逗留时间使用访问计数作为其分母。

因此，这些指标可能会在访问级别产生相似的结果，但在点击级别则将产生不同的结果。

## 百分比高于 100%

此指标通常包含高于 100% 的百分比。 分母是整个维度的每次访问逗留时间，分子是维度项目的每次访问逗留时间。 如果整个维度的每次访问逗留时间少于给定维度项目的每次访问逗留时间，您将看到高于 100% 的百分比。 按此指标对排名报表进行排序，可显示每次访问逗留时间的异常值，此值通常没什么价值。 Adobe 建议在排名报表中按其他指标（例如[访问次数](visits.md)）来排序。

有关逗留时间的更多常规信息，请参阅[逗留时间概述](time-spent.md)。
