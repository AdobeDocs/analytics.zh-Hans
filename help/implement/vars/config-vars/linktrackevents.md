---
title: linkTrackEvents
description: 确定链接跟踪图像请求中要包含的事件。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackEvents

某些实现不希望将所有变量包含在所有链接跟踪图像请求中。 使用和 [`linkTrackVars`](linktrackvars.md) 变量 `linkTrackEvents` 在调用中有选择地包含维度和 [`tl()`](../functions/tl-method.md) 度量。

此变量不用于页面查看调用(方[`t()`](../functions/t-method.md) 法)。

## 使用Adobe Experience Platform Launch进行链接跟踪调用中的事件

Launch会自动检测界面中定义的事件，并将其包含在链接跟踪点击中。

> [!IMPORTANT] 如果使用自定义代码编辑器在启动项中设置事件，则还必须在使用自定义代码 `linkTrackEvents` 的过程中包含该事件。

## AppMeasurement中的s.linkTrackEvents和启动自定义代码编辑器

变量 `s.linkTrackEvents` 是一个字符串，其中包含要包含在链接跟踪图像请求（方法）中的以逗号分隔的事件`tl()` 列表。 必须满足以下三个条件才能在链接跟踪点击中包含度量：

* 在变量中设置所需的 [`events`](../page-vars/events/events-overview.md) 事件。 例如：`s.events = "event1";`。
* Set the `events` variable in `linkTrackVars`. 例如：`s.linkTrackVars = "events";`。
* 在变量中设置所需的 `linkTrackEvents` 事件。 例如：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

此变量的默认值是空字符串。 如果未定义此变量，则链接跟踪图像请求中将包括所有事件。 请注意，Launch会根据界面中设置的事件自动填充此变量，因此始终在使用Launch的实现中设置它。

> [!TIP] 在此变量中指定事件时，请`s.`避免使用Analytics对象标识符()。 例如， `s.linkTrackEvents = "event1";` 正确，而错误 `s.linkTrackEvents = "s.event1";` 则正确。

## 示例

以下链接跟踪功能仅包 `event1` 括( `event2`非)发送到Adobe的图像请求：

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
