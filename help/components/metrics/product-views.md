---
title: 产品查看次数
description: 产品页面的查看次数。
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: eb13c3e828bc6d4c547f4529ee7a15182bbbf046
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 88%

---

# 产品查看次数

“产品查看次数”量度显示查看任何产品的次数。当您想要查看最常查看的产品，或查看一段时间内总产品查看趋势时，此量度很有用。

## 如何计算此量度

此量度计算符合以下&#x200B;**任一**&#x200B;情况的点击数：

* [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在值 `prodView`；或
* 此 [`products`](/help/implement/vars/page-vars/products.md) 变量设置，且 `events` 变量为空。
