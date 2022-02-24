---
title: 产品查看次数
description: 产品页面的查看次数。
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '94'
ht-degree: 100%

---

# 产品查看次数

“产品查看次数”量度显示查看任何产品的次数。当您想要查看最常查看的产品，或查看一段时间内总产品查看趋势时，此量度很有用。

## 如何计算此量度

此量度计算符合以下&#x200B;**任一**&#x200B;情况的点击数：

* [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在值 `prodView`；或
* 已设置 [`products`](/help/implement/vars/page-vars/products.md) 变量，且 `events` 变量中不存在购物车事件。任何非自定义事件 (`event1` - `event1000`) 都是购物车事件。
