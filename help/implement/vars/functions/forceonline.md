---
title: forceOnline
description: 手动设置AppMeasurement的联机状态。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# forceOnline

该方 `forceOnline` 法允许您覆盖自动检测到的AppMeasurement状态。

> [!IMPORTANT] 仅在启用时使 `trackOffline` 用此函数。 在脱机跟踪之外使用此函数可能会导致数据丢失。

AppMeasurement可自动检测设备的联机状态。 您可以使用该方 `forceOnline` 法强制AppMeasurement将点击视为设备处于联机状态。 此方法不采用任何参数，也不返回任何值。 它的唯一目的是覆盖AppMeasurement中的联机状态。

## 在Adobe Experience Platform Launch中强制在线

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.forceOnline()和启动自定义代码编辑器

在实例化Analytics对 `s.forceOnline()` 象后，您可以在实施中的任意位置调用该方法。

```js
s.forceOnline();
```
