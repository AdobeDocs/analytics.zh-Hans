---
title: 购物车
description: 访客将第一个产品添加到购物车的点击数。
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
TQID: https://experienceleague.adobe.com/a-qT5Ly8-4mSBGbGTAzbwLIMRFZtqotMPvGFgOrM41Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 45%

---

# 购物车

“购物车”[量度](overview.md)显示访客将其第一个产品添加到购物车的点击次数。

## 如何计算此指标

此指标计算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在 `scOpen` 的点击数。

## “购物车”、“购物车查看次数”和“购物车加货次数”的区别

由于“购物车”、“购物车查看次数”和“购物车加货”是需要实施的事件，贵组织会决定这些量度之间的确切差异。 但是，Adobe设计了这些量度的以下逻辑：

* 访客将第一个产品添加到其购物车后，“购物车”仅在每次购买时才会触发一次。
* 每次访客查看购物车时，都会触发“购物车查看”。
* “购物车加货”触发器适用于添加到购物车中的每个产品。

当客户将其第一个产品添加到购物车时，预期行为是“购物车”和“购物车加货”都会触发。 需要再次说明的是，这些指导方针不是具体操作；贵组织会确定确切的实施逻辑。
