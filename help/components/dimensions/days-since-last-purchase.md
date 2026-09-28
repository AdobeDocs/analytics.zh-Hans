---
title: 上次购买间隔天数
description: 当前点击与上次购买之间间隔的天数。
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: 'https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
ht-degree: 64%
---
# 上次购买间隔天数

“上次购买间隔天数”维度[维度](overview.md)测量访客的当前点击与他们当时最近购买之间间隔的时间。 此维度有助于您了解访客在网站上购物后的行为。

此维度中不包括从未购买过任何商品的访客。 此外，也不包括在访客首次购买前触发的点击。 仅包括访客首次购买后的点击。

## 使用数据填充此维度

Adobe根据访客的购买历史记录在服务器端计算此维度。 没有要设置的变量；它取决于您的网站上正在实施的[`purchase`](/help/implement/vars/page-vars/events/event-purchase.md)事件。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（由Adobe计算） |
| **Web SDK / XDM字段** | 无（由Adobe计算） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

## 维度项目

维度项目包括访客最近购买与当前点击之间间隔的天数。 每个天数都是一个单独的维度项，出现“同一天”即表示访客的最近购买与当前点击发生在同一天。
