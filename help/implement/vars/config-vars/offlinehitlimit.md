---
title: offlineHitLimit
description: 确定要置于离线跟踪队列的最大点击数。
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-uvCAqUO0A-7XjlemN4XwHXVG9DFK-UoVTW77up9-AY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 39%

---

# offlineHitLimit

离线跟踪是在 Adobe Analytics 中收集数据的一种可选方式。 如果访客断开与Internet的连接但继续浏览您的网站，则点击量会存储在离线队列中，直到设备重新连接到Internet为止。 离线跟踪主要用于移动设备应用程序。

`offlineHitLimit` 变量可对设备在本地存储的点击数设置上限。 仅在启用 [`trackOffline`](trackoffline.md) 时，此变量才有效。

## 使用Web SDK的离线点击限制

Web SDK不支持离线跟踪。

## 使用Adobe Analytics扩展的“离线点击限制”

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.offlineHitLimit

`s.offlineHitLimit`变量是一个整数，表示设备在离线状态下存储的最大点击数。 如果未定义此变量，则默认为`10`。 您可以将其设置为任意整数值。 设置高值时，请注意访客浏览器中的本地存储上限。 此限制通常为5 - 10 MB。

```js
s.offlineHitLimit = 100;
```
