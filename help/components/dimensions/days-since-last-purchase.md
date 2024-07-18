---
title: 上次购买间隔天数
description: 当前点击与上次购买之间间隔的天数。
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 84%

---

# 上次购买间隔天数

“上次购买间隔天数”维度[维度](overview.md)测量访客的当前点击与他们当时最近购买之间间隔的时间。 此维度有助于您了解访客在网站上购物后的行为。

此维度中不包括从未购买过任何商品的访客。此外，也不包括在访客首次购买前触发的点击。仅包括访客首次购买后的点击。

## 使用数据填充此维度

Adobe 会根据实施中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件，自动填充此维度。如果您在网站上实施了 `purchase` 事件，则此维度始终有效。

## 维度项目

维度项目包括访客最近购买与当前点击之间间隔的天数。每一天都是一个单独的维度项目，出现“同一天”即表示访客的最近购买与当前点击发生在同一天。
