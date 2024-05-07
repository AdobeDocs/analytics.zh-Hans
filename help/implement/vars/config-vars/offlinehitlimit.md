---
title: offlineHitLimit
description: 确定要置于离线跟踪队列的最大点击数。
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 8bc5e649c5b5852232f4baddcddad0766bc1569a
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 39%

---

# offlineHitLimit

离线跟踪是在 Adobe Analytics 中收集数据的一种可选方式。如果访客断开与Internet的连接但继续浏览您的网站，则点击量会存储在离线队列中，直到设备重新连接到Internet为止。 离线跟踪主要用于移动设备应用程序。

`offlineHitLimit` 变量可对设备在本地存储的点击数设置上限。仅在启用 [`trackOffline`](trackoffline.md) 时，此变量才有效。

## 使用Web SDK的离线点击限制

Web SDK不支持离线跟踪。

## 使用Adobe Analytics扩展的“离线点击限制”

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.offlineHitLimit

此 `s.offlineHitLimit` 变量是一个整数，表示设备在离线状态下存储的最大点击数。 如果未定义此变量，则默认为 `10`. 您可以将其设置为任意整数值。 设置高值时，请注意访客浏览器中的本地存储上限。 此限制通常为5 - 10 MB。

```js
s.offlineHitLimit = 100;
```
