---
title: Experience Cloud 访客 ID
description: 访客的Experience Cloud ID (ECID)，在Data Warehouse中可用。
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 21%

---

# Experience Cloud 访客 ID

“Experience Cloud访客ID”[维度](overview.md)为每个访客提供Experience Cloud ID (ECID)。 它是一个128位数字，由两个拼接的64位数字组成，补至19位。

>[!IMPORTANT]
>
>此维度只能在 Data warehouse 中使用。

## 使用数据填充此维度

此维度需要使用Experience Cloud ID服务(ECID)的实施。 它对应于数据馈送中的`mcvisid`列。 有关详细信息，请参阅[数据列引用](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。

## 维度项目

Dimension项目包括每位访客的Experience Cloud ID。
