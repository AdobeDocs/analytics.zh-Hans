---
title: offlineThrottleDelay
description: 确定设备恢复为在线状态时的点击频率。
feature: Variables
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 83%

---

# offlineThrottleDelay

离线跟踪是在 Adobe Analytics 中收集数据的一种可选方式。如果访客断开与 Internet 的连接但继续浏览您的网站，则点击量会存储在离线队列中，直到设备重新连接到 Internet 为止。离线跟踪主要用于移动设备应用程序。

当设备恢复为在线状态时，存储在设备上的所有点击都将被发送到 Adobe 数据收集服务器。如果已排队点击的数量过大，可能会潜在地影响旧设备的性能。使用 `offlineThrottleDelay` 变量可确定将已排队的点击发送到 Adobe 的频率。

## 使用Web SDK的离线限制延迟

Web SDK不支持离线跟踪。

## 使用Adobe Analytics扩展的“离线限制延迟”

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.offlineThrottleDelay

`s.offlineThrottleDelay` 变量是一个整数，它表示 AppMeasurement 在发送已排队两个点击之间等待的毫秒数。其默认值是 `0`，这意味着会同时发送所有已排队的点击。如果 `trackOffline` 为 `false`，则此变量不执行任何操作。

```js
s.offlineThrottleDelay = 500;
```
