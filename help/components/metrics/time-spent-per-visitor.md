---
title: 每位访客逗留时间（秒）
description: “每位访客逗留时间（秒）”量度显示访客在访客整个生命周期中与给定维度项目交互的平均时间。
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
TQID: https://experienceleague.adobe.com/NFmA2Q80h2WOTRwoJ882aFMG60y2HKngR0Ew0qnxb8o
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 182
ht-degree: 85%

---

# 每位访客逗留时间（秒）

[!UICONTROL 每位访客逗留时间（秒）] [指标](overview.md)显示访客在整个生命周期中与给定维度项目交互的平均时间。

此指标因其处理架构不同而在 Data Warehouse 中不可用。

## 如何计算此指标

此量度使用公式 [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md)。

## 百分比高于 100%

此指标通常包含高于 100% 的百分比。 分母是整个维度的每位访客逗留时间，分子是维度项目的每位访客逗留时间。 如果整个维度的每位访客逗留时间少于给定维度项目的每位访客逗留时间，您将看到高于 100% 的百分比。 按此量度对排名报表进行排序，会显示网站平均深度的异常值，该值通常没什么价值。 Adobe 建议在排名报表中按其他指标（例如[访问次数](visits.md)）来排序。

有关逗留时间的更多常规信息，请参阅[逗留时间概述](time-spent.md)。
