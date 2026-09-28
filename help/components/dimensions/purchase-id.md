---
title: 购买 ID
description: 购买的唯一标识符，在Data Warehouse中可用。
feature: Dimensions
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 18%
---
# 购买 ID

“购买ID”[维度](overview.md)为购买提供唯一标识符。

>[!IMPORTANT]
>
>此维度只能在 Data Warehouse 中使用。

## 使用数据填充此维度

使用[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)变量设置此维度。 它对应于数据馈送中的`purchaseid`列。 有关详细信息，请参阅[数据列引用](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) |
| **Web SDK / XDM字段** | [`commerce.order.purchaseID`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **查询参数** | [`purchaseID`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<purchaseId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 20字节 |
| **持久性** | 点击 |

## 维度项目

Dimension项目包括在您的网站上收集的购买ID。
