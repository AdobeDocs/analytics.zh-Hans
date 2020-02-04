---
title: offlineThrottleDelay
description: 确定设备恢复联机时的点击频率。
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

离线跟踪是在Adobe Analytics中收集数据的一种可选方式。 如果访客断开与Internet的连接但继续浏览您的站点，则点击量会存储在脱机队列中，直到设备重新连接到Internet。 离线跟踪主要用于移动应用程序。

当设备恢复联机时，存储在设备上的所有点击都将发送到Adobe数据收集服务器。 大量排队的点击可能会潜在地影响旧设备的性能。 使用该 `offlineThrottleDelay` 变量确定将排队的点击发送到Adobe的频率。

## Adobe Experience Platform启动中的脱机节流延迟

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和Launch自定义代码编辑器中的s.offlineThrottleDelay

该 `s.offlineThrottleDelay` 变量是一个整数，它表示AppMeasurement在发送排队的点击之间等待的毫秒数。 其默认值是， `0`这意味着所有排队的点击都会同时发送。 如果 `trackOffline` 是 `false`，则此变量不执行任何操作。

```js
s.offlineThrottleDelay = 500;
```
