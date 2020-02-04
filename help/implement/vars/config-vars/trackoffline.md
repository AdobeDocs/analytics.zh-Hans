---
title: trackOffline
description: 启用或禁用离线跟踪，这会更改AppMeasurement收集数据的方式。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackOffline

离线跟踪是在Adobe Analytics中收集数据的一种可选方式。 如果访客断开与Internet的连接但继续浏览您的站点，则点击量会存储在脱机队列中，直到设备重新连接到Internet。 离线跟踪主要用于移动应用程序。

变量 `trackOffline` 决定您是否要在实施中使用脱机跟踪。

> [!IMPORTANT] 在启用此变量之前，必须配置报表包以接受加盖时间戳的点击。 如果报表包不接受加盖时间戳的点击并且启用了此变量，则数据将丢失且无法恢复。

启用后，AppMeasurement使用以下过程将数据发送到Adobe:

* 在编译图像请求时，包括时间戳查询字符串参数。
* 如果设备无法连接到Adobe数据收集服务器，则点击将存储在设备上的本地。
* 在随后的每次点击中，AppMeasurement都会尝试向Adobe发送图像请求。
   * 如果它无法连接到Adobe数据收集服务器，则点击会添加到设备上的队列。
   * 如果它可以到达Adobe数据收集服务器，则会发送设备脱机时的点击和点击队列。

## 在Adobe Experience Platform Launch中跟踪脱机

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## s.trackOffline in appMeasurement and Launch自定义代码编辑器

该 `s.trackOffline` 变量是一个布尔值，它启用或禁用脱机跟踪。 Its default value is `false`. 如果要启用脱 `true` 机跟踪，请将此值设置为。

```js
s.trackOffline = true;
```
