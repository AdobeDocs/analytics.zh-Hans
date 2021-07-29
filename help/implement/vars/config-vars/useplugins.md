---
title: usePlugins
description: 启用或禁用 doPlugins() 函数。
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 76%

---

# usePlugins

如果启用了 `usePlugins`，则 [`doPlugins()`](../functions/doplugins.md) 函数将在 AppMeasurement 编译并将点击发送给 Adobe 之前运行。如果使用 `doPlugins()` 函数，则启用此变量。

## 在Adobe Experience Platform中使用使用标记的插件

数据收集UI中没有可使用此变量的专用字段。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 自定义代码编辑器中的 s.usePlugins

`s.usePlugins` 变量是一个布尔值，用于确定 AppMeasurement 是否调用 `doPlugins()` 函数。其默认值为 `false`。如果在实施中使用 `doPlugins()` 函数，则将此变量设置为 `true`。

```js
s.usePlugins = true;
```
