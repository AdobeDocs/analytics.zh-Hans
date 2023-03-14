---
title: usePlugins
description: 启用或禁用 doPlugins() 函数。
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 52%

---

# usePlugins

如果启用了 `usePlugins`，则 [`doPlugins()`](../functions/doplugins.md) 函数将在 AppMeasurement 编译并将点击发送给 Adobe 之前运行。如果使用 `doPlugins()` 函数，则启用此变量。

## 使用 `onBeforeEventSend` 使用Web SDK回调

虽然Web SDK没有布尔值来处理在将数据发送到Adobe之前执行的其他逻辑，但您可以注册 `onBeforeEventSend` 回调以修改数据。 参见 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 有关更多信息，请参阅Web SDK文档。

## 通过Adobe Analytics扩展使用插件

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.usePlugins

`s.usePlugins` 变量是一个布尔值，用于确定 AppMeasurement 是否调用 `doPlugins()` 函数。其默认值为 `false`。如果在实施中使用 `doPlugins()` 函数，则将此变量设置为 `true`。

```js
s.usePlugins = true;
```
