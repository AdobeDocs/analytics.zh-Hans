---
title: 购物车减货
description: 访客从购物车中删除产品的点击次数。
feature: Metrics
exl-id: 74b9677e-89c7-4409-8bd3-99707436def0
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 100%

---

# 购物车减货

“购物车减货”量度显示访客从购物车中删除商品的次数。当您想要了解转化漏斗中客户对产品不再感兴趣的部分时，此量度会很有帮助。

## 如何计算此量度

此量度计算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在 `scRemove` 的点击数。
