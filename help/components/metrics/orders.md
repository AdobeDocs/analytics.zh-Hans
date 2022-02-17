---
title: 订单数
description: 购买的次数。
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 100%

---

# 订单数

“订单数”量度显示网站上的购买事件总数。此量度对于电子商务网站衡量转化率至关重要。您可以将此量度与任何维度组合，以了解哪些维度项目对订单做出了贡献。例如，您可以看到促成购买的热门促销活动（使用[跟踪代码](../dimensions/tracking-code.md)维度）或热门搜索词（使用 [eVar](../dimensions/evar.md)）。

## 如何计算此量度

此量度计算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在 `purchase` 的点击数。
