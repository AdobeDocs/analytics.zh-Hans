---
title: 首次购买间隔天数
description: 访客首次访问与首次购买之间的间隔天数。
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 83%

---

# 首次购买间隔天数

“首次购买间隔天数” [维度](overview.md) 报告访客首次访问您的网站与购买商品之间的间隔天数。 例如，如果访客在首次访问后间隔一天购买商品，则任何后续访问或事件都属于“1 天”维度项目。

访客首次购买后，在访客 Cookie 的剩余生命周期内，它们属于同一维度项目。

## 使用数据填充此维度

Adobe 会根据实施中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件，自动填充此维度。如果您在网站上实施了 `purchase` 事件，则此维度始终有效。

## 维度项目

维度项目包括访客首次访问您的网站与首次购买之间的间隔天数。每一天都是一个单独的维度项目，出现“同一天”即表示访客的首次访问与首次购买发生在同一天。
