---
title: 单页面访问次数（维度）
description: 指示访问只包含单页面的标志。
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
TQID: 'https://experienceleague.adobe.com/mMxxlVpQi7IsSuxSZGijnvWeoqCa-ybf8otPRDf6AyQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 66%
---
# 单页面访问量

>[!BEGINSHADEBOX]

*此帮助页介绍“单页面访问量”如何作为[维度](overview.md)使用。 有关更多信息，请参阅[单页面访问量](../metrics/single-page-visits.md)量度。*

>[!ENDSHADEBOX]

“单页面访问量”维度报告只包含单个独特[页面](page.md)维度项目的访问次数。 它是[单页面访问量](../metrics/single-page-visits.md)量度的维度形式。

此维度最常用作[分段](../segmentation/seg-home.md)中的组件。 在报表中通常不使用它来作为维度。

## 使用数据填充此维度

Adobe通过评估每次访问是否包含单个唯一页面来计算此维度服务器端。 没有变量可供设置；它可开箱即用于所有实施。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（由Adobe计算） |
| **Web SDK / XDM字段** | 无（由Adobe计算） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

## 维度项目

唯一的维度项目是 `"Enabled"`。 如果访问只包含单页面，则点击将设置为此值。 此报表中忽略所有其他点击。
