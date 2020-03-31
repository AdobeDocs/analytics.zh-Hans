---
title: offlineThrottleDelay
description: 确定设备恢复为在线状态时的点击频率。
translation-type: ht
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

离线跟踪是在 Adobe Analytics 中收集数据的一种可选方式。如果访客断开与 Internet 的连接但继续浏览您的网站，则点击量会存储在离线队列中，直到设备重新连接到 Internet 为止。离线跟踪主要用于移动设备应用程序。

当设备恢复为在线状态时，存储在设备上的所有点击都将被发送到 Adobe 数据收集服务器。如果已排队点击的数量过大，可能会潜在地影响旧设备的性能。使用 `offlineThrottleDelay` 变量可确定将已排队的点击发送到 Adobe 的频率。

## Adobe Experience Platform Launch 中的“离线限制延迟”

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.offlineThrottleDelay

`s.offlineThrottleDelay` 变量是一个整数，它表示 AppMeasurement 在发送已排队两个点击之间等待的毫秒数。其默认值是 `0`，这意味着会同时发送所有已排队的点击。如果 `trackOffline` 为 `false`，则此变量不执行任何操作。

```js
s.offlineThrottleDelay = 500;
```
