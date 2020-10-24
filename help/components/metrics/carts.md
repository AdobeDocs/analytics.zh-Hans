---
title: 购物车
description: 访客将第一个产品添加到购物车的点击数。
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---


# 购物车

“购物车减货”量度显示访客从购物车中删除商品的次数。当您想要了解转化漏斗中客户对产品不再感兴趣的部分时，此量度会很有帮助。

## 如何计算此量度

此量度计算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在 `scOpen` 的点击数。

## “购物车”与“购物车查看次数”的区别

由于“购物车”和“购物车查看次数”是需要实施的事件，贵组织会决定这两个量度之间的确切差异。但是，Adobe 设计了以下这些量度：

* 访客将第一个产品添加到其购物车后，“购物车”仅在每次购买时才会触发一次。
* “购物车加货”触发器适用于添加到购物车中的每个产品。

对于第一个产品，会触发“购物车”和“购物车加货”。需要再次说明的是，这些指导方针不是具体操作；贵组织会确定确切的实施逻辑。
