---
title: 首次购买间隔天数
description: 访客首次访问与首次购买之间的间隔天数。
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 83%

---

# 首次购买间隔天数

“首次购买间隔天数”维度[维度](overview.md)报告访客首次访问您的网站与购买商品之间的间隔天数。 例如，如果访客在首次访问后间隔一天购买商品，则任何后续访问或事件都属于“1 天”维度项目。

访客首次购买后，在访客 Cookie 的剩余生命周期内，它们属于同一维度项目。

## 使用数据填充此维度

Adobe 会根据实施中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件，自动填充此维度。 如果您在网站上实施了 `purchase` 事件，则此维度始终有效。

## 维度项目

维度项目包括访客首次访问您的网站与首次购买之间的间隔天数。 每一天都是一个单独的维度项目，出现“同一天”即表示访客的首次访问与首次购买发生在同一天。
