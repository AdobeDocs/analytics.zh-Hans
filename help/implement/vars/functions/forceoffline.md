---
title: forceOffline
description: 手动设置 AppMeasurement 的在线状态。
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 100%

---

# forceOffline

`forceOffline()` 方法允许您覆盖自动检测到的 AppMeasurement 状态。

>[!WARNING]
>
>仅在启用 [`trackOffline`](../config-vars/trackoffline.md) 时才使用此函数。在离线跟踪之外使用此函数可能会导致数据丢失。

AppMeasurement 会自动检测设备的在线状态。您可以使用该 `forceOffline()` 方法强制 AppMeasurement 处理点击，如同设备处于离线状态一样。此方法不接受任何参数，也不返回任何值。它的唯一用途是覆盖 AppMeasurement 中的在线状态。

## 使用 Adobe Experience Platform 中的标记的“强制离线”

数据收集 UI 中没有专门的字段来使用此变量。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和自定义代码编辑器中的 s.forceOffline()

在实例化 Analytics 对象后，您可以在实施中的任意位置调用 `s.forceOffline()` 方法。

```js
s.forceOffline();
```
