---
title: 首次购买间隔天数
description: 访客首次访问与首次购买之间的间隔天数。
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: 'https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
source-wordcount: '207'
ht-degree: 63%
---
# 首次购买间隔天数

“首次购买间隔天数”维度[维度](overview.md)报告访客首次访问您的网站与购买商品之间的间隔天数。 例如，如果访客在首次访问后间隔一天购买商品，则任何后续访问或事件都属于“1 天”维度项目。

访客首次购买后，在访客 Cookie 的剩余存留期内，始终属于同一维度项。

## 使用数据填充此维度

Adobe根据访客的购买历史记录在服务器端计算此维度。 没有要设置的变量；它取决于您的网站上正在实施的[`purchase`](/help/implement/vars/page-vars/events/event-purchase.md)事件。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（由Adobe计算） |
| **Web SDK / XDM字段** | 无（由Adobe计算） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 访客 |

## 维度项目

维度项目包括访客首次访问您的网站与首次购买之间的间隔天数。 每个天数值都是一个单独的维度项，出现“同一天”即表示访客的首次访问与首次购买发生在同一天。
