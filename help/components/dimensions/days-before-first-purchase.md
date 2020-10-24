---
title: 首次购买间隔天数
description: 访客首次访问与首次购买之间的间隔天数。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '173'
ht-degree: 100%

---


# 首次购买间隔天数

“首次购买间隔天数”维度报告访客首次访问您的网站与购买商品之间的间隔天数。例如，如果访客在首次访问后间隔一天购买商品，则任何后续访问或事件都属于“1 天”维度项目。

访客首次购买后，在访客 Cookie 的剩余生命周期内，它们属于同一维度项目。

## 使用数据填充此维度

Adobe 会根据实施中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件，自动填充此维度。如果您在网站上实施了 `purchase` 事件，则此维度始终有效。

## 维度项目

维度项目包括访客首次访问您的网站与首次购买之间的间隔天数。每一天都是一个单独的维度项目，出现“同一天”即表示访客的首次访问与首次购买发生在同一天。
