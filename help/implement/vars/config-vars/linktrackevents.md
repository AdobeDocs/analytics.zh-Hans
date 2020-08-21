---
title: linkTrackEvents
description: 确定要包含在链接跟踪图像请求中的事件。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '246'
ht-degree: 100%

---


# linkTrackEvents

某些实施不希望将所有变量包含在所有链接跟踪图像请求中。使用 [`linkTrackVars`](linktrackvars.md) 和 `linkTrackEvents` 变量可在 [`tl()`](../functions/tl-method.md) 调用中有选择地包含维度和量度。

页面查看调用（[`t()`](../functions/t-method.md) 方法）不使用此变量。

## 使用 Adobe Experience Platform Launch 的链接跟踪调用中的事件

Launch 会自动检测界面中定义的事件，并将其包含在链接跟踪点击中。

>[!IMPORTANT]
>
>如果使用自定义代码编辑器在 Launch 中设置事件，则还必须使用自定义代码在 `linkTrackEvents` 中包含该事件。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkTrackEvents

`s.linkTrackEvents` 变量是一个字符串，其中包含以逗号分隔的事件列表，您要将这些事件包含在链接跟踪图像请求（`tl()` 方法）中。必须满足以下三个条件才能在链接跟踪点击中包含量度：

* 在 [`events`](../page-vars/events/events-overview.md) 变量中设置所需事件。例如：`s.events = "event1";`。
* 在 `linkTrackVars` 中设置 `events` 变量。例如：`s.linkTrackVars = "events";`。
* 在 `linkTrackEvents` 变量中设置所需事件。例如：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

此变量的默认值是空字符串。如果未定义此变量，则链接跟踪图像请求中将包括所有事件。请注意，Launch 会根据界面中设置的事件自动填充此变量，因此实施始终使用 Launch 来设置此变量。

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
