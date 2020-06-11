---
title: 首次购买前几天
description: 访客首次访问与首次购买之间的天数。
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# 首次购买前几天

“首次购买前的天数”维度报告访客首次访问您的站点和进行购买之间的天数。 例如，如果访客在首次访问后的某一天购买产品，则任何后续访问或事件都属于“1天”维值。

在访客首次购买后，在访客的cookie生命周期的剩余时间内，他们属于相同的维度值。

## 用数据填充此维

Adobe会根据您实施中的事件自 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 动填充此维度。 如果您在站点 `purchase` 上实施事件，则此维始终有效。

## 维值

维度值包括访客首次访问您的站点与首次购买之间的天数。 每天数都是一个单独的维度值，“当天”发生在访客第一次访问和第一次购买发生在同一天。
