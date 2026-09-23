---
title: 月中几号
description: 月份的日期数字，不管是哪个月份。
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
TQID: https://experienceleague.adobe.com/jSrKlf4a5f-6MTrQwwUcvRJep4chAUyOsj5hFjE1HRg
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
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 63%
---
# 月中几号

“日期”[维度](overview.md)将任何给定月份的日期数字报告为维度项目。 例如，如果某个报表的时间跨度为 1 月 1 日至 3 月 31 日，则每个月的第一天会分组到同一个维度项目中。 当您希望报告按天细分，但不希望将静态日期作为维度项目时，此报告很有价值。 由于此维度会随着选定日期范围滚动，因此，将其作为计划报表中的维度特别有价值。

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

维度项目包括数字 `1` - `31`，表示点击在一个月中发生的日期。
