---
title: 每周的某一日
description: 一周中的某一天，与日期范围无关。
feature: Dimensions
exl-id: 01aa6b5f-49e6-4f86-97c7-8d0ff431e15b
TQID: 'https://experienceleague.adobe.com/9nudTrYTDMEFXSo81uUuw9KFT3mRPhZer3cX81AwoPM'
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
source-wordcount: '167'
ht-degree: 62%
---
# 每周的某一日

“每周时间”[维度](overview.md)报告点击在一周中发生的时间。 当您希望报表按周划分，但不希望静态天数作为维度项目时，此报表很有价值。 由于此维度适用于任何日期范围，因此，将其作为计划报表中的维度特别有价值。

## 使用数据填充此维度

此维度从每次点击的时间戳派生。 没有要设置的变量；它可以在任何实施中开箱即用。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自点击时间戳） |
| **Web SDK / XDM字段** | 无（派生自点击时间戳） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 点击 |

## 维度项目

维度项目包括 `Sunday` - `Saturday`，表示点击在一周中发生的时间。 默认情况下，维度项目的顺序以[自定义日历](/help/admin/tools/manage-rs/edit-settings/general/custom-calendar.md)中一周的第一天为准。
