---
title: offlineHitLimit
description: 确定离线跟踪队列的最大点击数。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

离线跟踪是在Adobe Analytics中收集数据的可选方式。 如果访客断开与Internet的连接但继续浏览您的站点，则点击量会存储在脱机队列中，直到设备重新连接到Internet。 离线跟踪主要用于移动应用程序。

该 `offlineHitLimit` 变量对设备本地存储的点击数设置上限。 此变量仅在启用时 [`trackOffline`](trackoffline.md) 有效。

## Adobe Experience Platform Launch中的脱机点击限制

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.offlineHitLimit和启动自定义代码编辑器

该 `s.offlineHitLimit` 变量是一个整数，表示设备在脱机状态下存储的最大点击数。 如果未定义此变量，则对设备在脱机状态下存储的点击数没有限制。

```js
s.offlineHitLimit = 100;
```
