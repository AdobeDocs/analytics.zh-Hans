---
title: usePlugins
description: 启用或禁用 doPlugins() 函数。
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/7ofbF5EloAUlvCmGv-CaTFxxZELX0wydJ8HzmU2f6EQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 32%

---

# usePlugins

如果启用了 `usePlugins`，则 [`doPlugins()`](../functions/doplugins.md) 函数将在 AppMeasurement 编译并将点击发送给 Adobe 之前运行。 如果使用 `doPlugins()` 函数，则启用此变量。

## 使用Web SDK的`onBeforeEventSend`回调

虽然Web SDK没有布尔值来处理在将数据发送到Adobe之前执行的其他逻辑，但您可以注册`onBeforeEventSend`回调以修改数据。 有关详细信息，请参阅Web SDK文档中的[全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hans#modifying-events-globally)。

## 通过Adobe Analytics扩展使用插件

Adobe提供了一个标记为“常用Analytics插件”的扩展，通过该扩展可调用大多数[插件](../plugins/impl-plugins.md)。 安装该扩展，并在规则中调用所需的插件。

如果Adobe扩展中未包含所需的插件，请按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.usePlugins

`s.usePlugins` 变量是一个布尔值，用于确定 AppMeasurement 是否调用 `doPlugins()` 函数。 其默认值为 `false`。 如果在实施中使用 `doPlugins()` 函数，则将此变量设置为 `true`。

```js
s.usePlugins = true;
```
