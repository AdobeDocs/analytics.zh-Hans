---
title: forceOffline
description: 手动设置 AppMeasurement 的在线状态。
feature: Appmeasurement Implementation
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---

# forceOffline

`forceOffline()` 方法允许您覆盖自动检测到的 AppMeasurement 状态。

>[!WARNING]
>
>仅在启用 [`trackOffline`](../config-vars/trackoffline.md) 时才使用此函数。在离线跟踪之外使用此函数可能会导致数据丢失。

AppMeasurement 会自动检测设备的在线状态。您可以使用该 `forceOffline()` 方法强制 AppMeasurement 处理点击，如同设备处于离线状态一样。此方法不接受任何参数，也不返回任何值。它的唯一用途是覆盖 AppMeasurement 中的在线状态。

## 使用Web SDK强制离线

Web SDK不支持离线跟踪。

## 使用Adobe Analytics扩展强制离线

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.forceOffline()

在实例化 Analytics 对象后，您可以在实施中的任意位置调用 `s.forceOffline()` 方法。

```js
s.forceOffline();
```
