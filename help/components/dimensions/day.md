---
title: 日
description: 量度出现的日期。
feature: Dimensions
exl-id: 2f93ae8b-422c-4e1e-81d3-43cc0aa442c4
TQID: 'https://experienceleague.adobe.com/q9gioxGcmj2xB-yamZUyM3jLLlTpT4NHq1CFCMqm-6I'
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
source-wordcount: '149'
ht-degree: 59%
---
# 日

“日”[维度](overview.md)报告给定量度出现的日期。 第一个维度项目是日期范围内的第一天，最后一个维度项目是日期范围内的最后一天。 此维度对趋势报表而言非常重要，因为它允许您查看一段时间内的量度变化情况。

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

维度项包括给定某一天的日期。 它包含年、月、日，作为维度项的一部分。
