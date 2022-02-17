---
title: offlineHitLimit
description: 确定要置于离线跟踪队列的最大点击数。
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 100%

---

# offlineHitLimit

离线跟踪是在 Adobe Analytics 中收集数据的一种可选方式。如果访客断开与 Internet 的连接但继续浏览您的网站，则点击量会存储在离线队列中，直到设备重新连接到 Internet 为止。离线跟踪主要用于移动设备应用程序。

`offlineHitLimit` 变量可对设备在本地存储的点击数设置上限。仅在启用 [`trackOffline`](trackoffline.md) 时，此变量才有效。

## 使用 Adobe Experience Platform 中的标记的“离线点击限制”

数据收集 UI 中没有专门的字段来使用此变量。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和自定义代码编辑器中的 s.offlineHitLimit

`s.offlineHitLimit` 变量是一个整数，表示设备在离线状态下存储的最大点击数。如果未定义此变量，则对设备在离线状态下存储的点击数没有限制。

```js
s.offlineHitLimit = 100;
```
