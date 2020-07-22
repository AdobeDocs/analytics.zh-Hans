---
title: 上次购买后的天数
description: 当前点击与他们上次购买之间的天数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# 上次购买后的天数

“上次购买后的天数”维度测量访客的当前点击与当时的最新购买之间的时间。 此维度有助于您了解访客在网站上购买商品后所做的行为。

从未购买过某些内容的访客不包括在此维度中。 此外，访客首次购买前触发的点击也不包括。 仅包含访客首次购买后的点击。

## 用数据填充此维

Adobe会根据您实施中的事件自 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 动填充此维度。 如果您在站点 `purchase` 上实施事件，则此维始终有效。

## 维项

维项目包括访客最近购买与当前点击之间的天数。 每个天数是单独的维度项目，“同一天”发生在访客最近购买和当前点击发生在同一天。
