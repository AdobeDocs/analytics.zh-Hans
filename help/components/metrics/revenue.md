---
title: 收入
description: 所有订单中已购买产品的货币金额。
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 88%

---

# 收入

“收入”[量度](overview.md)显示所有订单中购买产品的货币金额。 此量度对于电子商务网站衡量转化率至关重要。您可以将此量度与任何维度组合，以了解哪些维度项目对收入做出了贡献。例如，您可以看到热门促销活动（使用[跟踪代码](../dimensions/tracking-code.md)维度）或热门内部搜索词（使用 [eVar](../dimensions/evar.md)）。

## 如何计算此量度

至于 [`events`](/help/implement/vars/page-vars/events/event-purchase.md) 变量中存在 `purchase` 的每次点击，对 [`products`](/help/implement/vars/page-vars/products.md) 变量中的“价格”字段求和。

如果页面上的货币与报表包的原生货币不同，则此度量取决于 [currencyCode](/help/implement/vars/config-vars/currencycode.md) 变量。
