---
title: 产品查看次数
description: 产品页面的查看次数。
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
TQID: https://experienceleague.adobe.com/bspBkiEAfkwBQwWV3-KoDKDRNGLogCKkSXvY2Cpyv-M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 80
ht-degree: 72%

---

# 产品查看次数

“产品查看次数”[量度](overview.md)显示查看任何产品的次数。 当您想要查看最常查看的产品，或查看一段时间内总产品查看趋势时，此量度很有用。

## 如何计算此指标

此量度计算符合以下&#x200B;**任一**&#x200B;情况的点击数：

* [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在值 `prodView`；或
* 已设置[`products`](/help/implement/vars/page-vars/products.md)变量，`events`变量为空。
