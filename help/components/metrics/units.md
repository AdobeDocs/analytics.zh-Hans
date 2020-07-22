---
title: 件数
description: 所有订单内购买的产品总数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# 件数

“Units”量度显示所有订单内购买的产品总数。 此指标对于电子商务站点衡量转化率至关重要。 您可以将此指标与任何维度相结合，以查看哪些维度项目对购买的产品数量做出了贡献。 例如，您可以看到贡献于所购买产品的顶 [级活动](../dimensions/tracking-code.md) （使用跟踪代码维）或顶级内部搜索 [词(使](../dimensions/evar.md)用eVar)。

## 如何计算此度量

对于变量中 `purchase` 存在的每 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 次点击，在变量中求和“数量”字 [`products`](/help/implement/vars/page-vars/products.md) 段。

## 比较订单和单位

“订 [单](orders.md) ”量度仅记录采购事件数。 “件数”指标通常比“订单”高，因为客户可以购买多个产品。 在这些情况下，单个订单具有多个单位。

如果您的订购量高于单位，Adobe建议您检查实施的完整性。 可能在购买时 `products` 未正确设置变量，这通常是不需要的行为。
