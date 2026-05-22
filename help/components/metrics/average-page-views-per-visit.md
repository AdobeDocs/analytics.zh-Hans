---
title: 每次访问的平均页面查看次数
description: 给定维度项目在一次访问中出现的平均次数。
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
TQID: https://experienceleague.adobe.com/sospsPhk77O5qOLcMLmu7gB7rvlxbp8rGqB39LCnQ5g
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 92%

---

# 每次访问的平均页面查看次数

“每次访问的平均页面查看次数”维度显示针对所需维度平均查看页面的次数。 对于基于时间的维度，您可以查看访问中一段时间内平均页面查看次数的趋势。 当您想要了解维度项目在访问中出现的频率时，此[量度](overview.md)非常有用。

>[!TIP]
>
>将此量度与其他量度（例如[访问数](visits.md)）一起使用以获取更好的洞察。 如果您单独使用此量度，则会获得包含每次访问异常页面查看次数的维度项目，该维度项目通常没有什么价值。

## 如何计算此指标

使用公式 [`Page views`](page-views.md)` divided by `[`Visits`](visits.md) 计算此量度。

## 百分比高于 100%

此指标通常包含高于 100% 的百分比。 分母是整个维度的每次访问平均页面查看次数，分子是维度项目的每次访问平均页面查看次数。 如果整个维度的每次访问平均页面查看次数少于给定维度项目的每次访问平均页面查看次数，您将看到高于 100% 的百分比。 按此量度对排名报表进行排序，会显示每次访问平均页面查看次数的异常值，该值通常没什么价值。 Adobe 建议在排名报表中按其他量度（例如[访问次数](visits.md)）来排序。
