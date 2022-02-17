---
title: trackOffline
description: 启用或禁用离线跟踪，这会更改 AppMeasurement 收集数据的方式。
feature: Variables
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

---

# trackOffline

离线跟踪是在 Adobe Analytics 中收集数据的一种可选方式。如果访客断开与 Internet 的连接但继续浏览您的网站，则点击量会存储在离线队列中，直到设备重新连接到 Internet 为止。离线跟踪主要用于移动设备应用程序。

`trackOffline` 变量可决定您是否要在实施中使用离线跟踪。

>[!IMPORTANT]
>
> 在启用此变量之前，必须配置报表包以接受带有时间戳的点击。如果报表包不接受带有时间戳的点击并且已启用此变量，则数据将丢失且无法恢复。

启用后，AppMeasurement 使用以下过程将数据发送到 Adobe：

* 在编译图像请求时，将包含时间戳查询字符串参数。
* 如果设备无法访问 Adobe 数据收集服务器，则将点击存储在设备本地。
* 在随后的每次点击中，AppMeasurement 都会尝试将图像请求发送到 Adobe。
   * 如果无法访问 Adobe 数据收集服务器，则会将点击添加到设备上的队列中。
   * 如果可以访问 Adobe 数据收集服务器，则会发送设备处于离线状态时的点击和点击队列。

## 使用 Adobe Experience Platform 中的标记的“跟踪离线”

数据收集 UI 中没有专门的字段来使用此变量。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和自定义代码编辑器中的 s.trackOffline

`s.trackOffline` 变量是一个布尔值，用于启用或禁用离线跟踪。其默认值为 `false`。如果要启用离线跟踪，则将此值设置为 `true`。

```js
s.trackOffline = true;
```
