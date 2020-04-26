---
title: offlineHitLimit
description: 确定要置于离线跟踪队列的最大点击数。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

离线跟踪是在 Adobe Analytics 中收集数据的一种可选方式。如果访客断开与 Internet 的连接但继续浏览您的网站，则点击量会存储在离线队列中，直到设备重新连接到 Internet 为止。离线跟踪主要用于移动设备应用程序。

`offlineHitLimit` 变量可对设备在本地存储的点击数设置上限。This variable only works if [`trackOffline`](trackoffline.md) is enabled.

## Adobe Experience Platform Launch 中的“离线点击限制”

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.offlineHitLimit

`s.offlineHitLimit` 变量是一个整数，表示设备在离线状态下存储的最大点击数。如果未定义此变量，则对设备在离线状态下存储的点击数没有限制。

```js
s.offlineHitLimit = 100;
```
