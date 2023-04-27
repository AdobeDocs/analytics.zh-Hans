---
title: usePlugins
description: 启用或禁用 doPlugins() 函数。
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 41154580c272514e504c5478215bb67795488de3
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 33%

---

# usePlugins

如果启用了 `usePlugins`，则 [`doPlugins()`](../functions/doplugins.md) 函数将在 AppMeasurement 编译并将点击发送给 Adobe 之前运行。如果使用 `doPlugins()` 函数，则启用此变量。

## 使用 `onBeforeEventSend` 使用Web SDK回调

虽然Web SDK没有布尔值来处理在将数据发送到Adobe之前执行其他逻辑，但您可以注册 `onBeforeEventSend` 回调以修改数据。 请参阅 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) （位于Web SDK文档中）以了解更多信息。

## 使用Adobe Analytics扩展的插件

Adobe提供了一个标有“常用Analytics插件”的扩展，通过该扩展，您可以调用 [插件](../plugins/impl-plugins.md). 安装扩展，然后在规则中调用所需的插件。

如果Adobe扩展中未包含所需的插件，请按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展的s.usePlugins自定义代码编辑器

`s.usePlugins` 变量是一个布尔值，用于确定 AppMeasurement 是否调用 `doPlugins()` 函数。其默认值为 `false`。如果在实施中使用 `doPlugins()` 函数，则将此变量设置为 `true`。

```js
s.usePlugins = true;
```
