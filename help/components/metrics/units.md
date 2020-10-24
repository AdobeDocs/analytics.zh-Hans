---
title: 件数
description: 所有订单内购买的产品总数。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '174'
ht-degree: 100%

---


# 件数

“件数”量度显示所有订单内购买的产品总数。此量度对于电子商务网站衡量转化率至关重要。您可以将此量度与任何维度组合，以了解哪些维度项目对购买的产品数量做出了贡献。例如，您可以看到促进产品购买的热门营销活动（使用[跟踪代码](../dimensions/tracking-code.md)维度）或热门内部搜索词（使用 [eVar](../dimensions/evar.md)）。

## 如何计算此量度

对于 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在 `purchase` 的每次点击，计算 [`products`](/help/implement/vars/page-vars/products.md) 变量中“数量”字段的和。

## 比较订单数和件数

[订单数](orders.md)量度仅记录采购事件数。“件数”量度通常比“订单数”高，因为客户可能购买多个产品。在这种情况下，单个订单具有多个件数。

如果您的订单数高于件数，Adobe 建议您检查实施的完整性。可能未对购买正确设置 `products` 变量，这通常是不需要的行为。
