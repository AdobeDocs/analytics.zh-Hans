---
title: usePlugins
description: 启用或禁用doPlugins()函数。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# usePlugins

如果 `usePlugins` 启用此功能，则该函 [`doPlugins()`](../functions/doplugins.md) 数会在AppMeasurement编译前运行，并向Adobe发送点击。 如果使用函数，请启用此 `doPlugins()` 变量。

## 使用Adobe Experience Platform Launch中的插件

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## s.usePlugins in AppMeasurement and Launch自定义代码编辑器

该 `s.usePlugins` 变量是一个布尔值，它确定AppMeasurement是否调用该 `doPlugins()` 函数。 Its default value is `false`. 如果在实现中 `true` 使用该函数，请将 `doPlugins()` 此变量设置为。

```js
s.usePlugins = true;
```
