---
title: 产品
description: 产品的名称。
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: 'https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc'
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
source-wordcount: '191'
ht-degree: 58%
---
# 产品

“产品”[维度](overview.md)报告点击中产品的名称。 此维度对于使用 `products` 变量且想要查看产品相关量度（例如，最畅销的产品或查看次数最多的产品）的实施非常有用。 如果您的网站上没有任何产品，则此维度可能会特意留空。

## 使用数据填充此维度

此维度引用[`products`](/help/implement/vars/page-vars/products.md)变量中的产品名称，该变量是第一个和第二个分号(`;`)之间的字符串。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`products`](/help/implement/vars/page-vars/products.md) |
| **Web SDK / XDM字段** | [`productListItems[].name`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **查询参数** | [`products`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<products>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 100字节 |
| **持久性** | 点击 |

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。 Adobe 建议为产品确立一致的命名约定。 如果想对产品进行不同分组或为其提供更友好的名称，则可以使用[分类](../classifications/classifications-overview.md)。 Adobe 建议同时使用“产品”和“类别”维度。
