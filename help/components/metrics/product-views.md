---
title: 产品视图
description: 产品页面的视图数。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---


# 产品视图

“产品视图”指标显示查看任何产品的次数。 当您想要查看您最常查看的产品，或查看总产品视图随时间变化的趋势时，此指标很有用。

## 如何计算此度量

此度量计算与以下任一项匹 **配** 的点击数：

* 该值存 `prodView` 在于变 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 量中； 或
* 变量 [`products`](/help/implement/vars/page-vars/products.md) 已设置，且变量中不存在购物车事件 `events` 符。 任何非自定义事件(`event1` - `event1000`)都是购物车事件。