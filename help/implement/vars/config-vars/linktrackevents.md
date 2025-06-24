---
title: linkTrackEvents
description: 确定要包含在链接跟踪图像请求中的事件。
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 68%

---

# linkTrackEvents

某些实施不希望将所有变量包含在所有链接跟踪图像请求中。使用 [`linkTrackVars`](linktrackvars.md) 和 `linkTrackEvents` 变量可在 [`tl()`](../functions/tl-method.md) 调用中有选择地包含维度和量度。

页面查看调用（[`t()`](../functions/t-method.md) 方法）不使用此变量。

## 使用Web SDK确定要包含在XDM事件中的Analytics事件

Web SDK不排除链接跟踪调用的某些字段。 但是，您可以在将数据发送到Adobe之前使用`onBeforeEventSend`回调清除或设置所需字段。 有关详细信息，请参阅Web SDK文档中的[全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)。

## 使用Adobe Analytics扩展程序的链接跟踪调用中的事件

如果您不使用自定义代码，Adobe Experience Platform 会自动将定义的事件包含在链接跟踪点击中。

>[!IMPORTANT]
>
>如果您在Analytics扩展的自定义代码编辑器中设置事件，则还必须使用自定义代码在`linkTrackEvents`中包含该事件。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.linkTrackEvents

`s.linkTrackEvents` 变量是一个字符串，其中包含以逗号分隔的事件列表，您要将这些事件包含在链接跟踪图像请求（`tl()` 方法）中。必须满足以下三个条件才能在链接跟踪点击中包含量度：

* 在 [`events`](../page-vars/events/events-overview.md) 变量中设置所需事件。例如：`s.events = "event1";`。
* 在 `linkTrackVars` 中设置 `events` 变量。例如：`s.linkTrackVars = "events";`。
* 在 `linkTrackEvents` 变量中设置所需事件。例如：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

此变量的默认值是空字符串。如果未定义此变量，则链接跟踪图像请求中将包括所有事件。请注意，数据收集会根据界面中设置的事件自动填充此变量，因此始终为使用 Adobe Experience Platform 中的标记的实施设置此变量。

>[!TIP]
>
>在此变量中指定事件时，请避免使用 Analytics 对象标识符 (`s.`)。例如，`s.linkTrackEvents = "event1";` 是正确的，而 `s.linkTrackEvents = "s.event1";` 是错误的。

## 示例

以下链接跟踪函数在发送到 Adobe 的图像请求中仅包含 `event1`（不包含 `event2`）：

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
