---
title: 购物车
description: 访客将其第一个产品添加到购物车的点击数。
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# 购物车

“购物车删除”量度显示访客从购物车中删除物品的次数。 当您想要了解客户对产品不再感兴趣的转化漏斗的部分时，此指标会很有帮助。

## 如何计算此度量

此度量计算变量中存 `scOpen` 在的点击 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 数。

## “购物车”与“购物车视图”的区别

由于“购物车”和“购物车视图”是需要实施的事件，您的组织将决定这两个指标之间的确切差异。 但是，Adobe为以下方面设计了这些指标：

* “购物车”在访客将其第一个产品添加到其购物车时，每次购买只触发一次。
* “购物车加货”触发器用于添加到购物车中的每个产品。

对于第一个产品，“购物车”和“购物车加货”触发器。 同样，这些指导方针并不具体； 您的组织确定确切的实施逻辑。
