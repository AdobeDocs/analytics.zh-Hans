---
title: 客户忠诚度
description: 基于访客先前购买次数的类别。
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 88%

---

# 客户忠诚度

“客户忠诚度”[维度](overview.md)报告以前购买过0次、以前购买过1次、以前购买过2次或以前购买过3次以上的网站的访客数。 此维度对于了解网站对购买行为的影响程度非常有价值。 此外，您还可以在区段中使用此维度来重点关注返回网站进行购买的访客，以便鼓励新访客的类似行为。

## 使用数据填充此维度

Adobe 会根据实施中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件，自动填充此维度。 如果您在网站上实施了 `purchase` 事件，则此维度始终有效。

## 维度项目

维度项目包括：

* **不是客户**：在点击时，访客以前从未购买过商品。
* **新客户**：在点击时，访客以前只购买过一次。
* **回头客户**：在点击时，访客以前购买过两次。
* **忠诚客户**：在点击时，访客以前购买过三次或更多次。

当访客购买商品（触发 `purchase` 事件）时，该点击和所有后续点击将移至下一个“分段”。 例如，如果访客首次从您的网站购买商品，则他们会从“不是客户”移动到“新客户”，并且此订单归因于“新客户”。 不能将订单归因于维度项目“不是客户”。
