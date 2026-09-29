---
title: 发生事件之前逗留的时间
description: 量度与访问的首次点击之间的间隔时间。
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: 'https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0'
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
source-wordcount: '197'
ht-degree: 53%
---
# 发生事件之前逗留的时间

“发生事件之前逗留的时间”维度[维度](overview.md)报告访问的首次点击与所需量度之间经过的时间量。 确定达到成功事件（例如，提交表单或购买）所花费的时间时，此维度非常有用。

## 使用数据填充此维度

Adobe根据访问的首次点击与target事件之间经过的时间，计算此维度服务器端。 没有要设置的变量。 虽然从技术上讲，它可开箱即用，但在您的网站上实施自定义和购买事件时，它可提供最佳效果。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（由Adobe计算） |
| **Web SDK / XDM字段** | 无（由Adobe计算） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

## 维度项目

维度项目包括基于时间的时段，介于 `"Less than 1 minute"` 到 `"More than 15 hours"` 之间。 例如，如果访客从第一次点击到购买用了 23 分钟，则它属于 `"10 to 30 minutes"` 维度项目下。 无法为此量度自定义存储桶。
