---
title: 订单数
description: 购买的次数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 80%

---


# 订单数

“订单数”量度显示网站上的购买事件总数。此量度对于电子商务网站衡量转化率至关重要。您可以将此度量与任何维度组合，以查看哪些维度项贡献了订单。 例如，您可以看到促成购买的热门促销活动（使用[跟踪代码](../dimensions/tracking-code.md)维度）或热门搜索词（使用 [eVar](../dimensions/evar.md)）。

## 如何计算此量度

此量度计算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在 `purchase` 的点击数。
