---
title: 件数
description: 所有订单内购买的产品总数。
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
TQID: https://experienceleague.adobe.com/0v4pF0Iv0IzU9K4CQiTy1-IIYgMCaO37E6QTmAAEPXc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 80%

---

# 件数

“件数”[量度](overview.md)显示所有订单中购买的产品总数。 此量度对于电子商务网站衡量转化率至关重要。 您可以将此量度与任何维度组合，以了解哪些维度项目对购买的产品数量做出了贡献。 例如，您可以看到促进产品购买的热门营销活动（使用[跟踪代码](../dimensions/tracking-code.md)维度）或热门内部搜索词（使用 [eVar](../dimensions/evar.md)）。

## 如何计算此指标

对于 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在 `purchase` 的每次点击，计算 [`products`](/help/implement/vars/page-vars/products.md) 变量中“数量”字段的和。

## 比较订单数和件数

[订单数](orders.md)量度仅记录采购事件数。 “件数”量度通常比“订单数”高，因为客户可能购买多个产品。 在这种情况下，单个订单具有多个件数。

如果您的订单数高于件数，Adobe 建议您检查实施的完整性。 可能未对购买正确设置 `products` 变量，这通常是不需要的行为。
