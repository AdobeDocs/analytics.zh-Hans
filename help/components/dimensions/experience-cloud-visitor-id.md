---
title: Experience Cloud 访客 ID
description: 访客的Experience Cloud ID (ECID)，在Data Warehouse中可用。
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 18%
---
# Experience Cloud 访客 ID

“Experience Cloud访客ID”[维度](overview.md)为每个访客提供ECID。 它是一个128位数字，由两个拼接的64位数字组成，补至19位。

>[!IMPORTANT]
>
>此维度只能在 Data Warehouse 中使用。

## 使用数据填充此维度

此维度要求实施使用访客ID服务(VisitorAPI)或Experience Platform Identity服务。 它对应于数据馈送中的`mcvisid`列。 有关详细信息，请参阅[数据列引用](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（由Experience Cloud访客ID服务设置） |
| **Web SDK / XDM字段** | 无（由Experience Cloud Identity服务设置） |
| **查询参数** | [`mid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<marketingCloudVisitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

## 维度项目

Dimension项目包括每位访客的Experience Cloud ID。
