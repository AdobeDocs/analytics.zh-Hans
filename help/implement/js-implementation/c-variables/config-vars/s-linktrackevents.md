---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkTrackEvents

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

在指向 [!DNL help.php] 的第一个链接中，注意事件变量保留了在点击链接前设置的值，这样可允许 event1 随自定义链接一起发送。在第二个示例，即指向 [!DNL test.php] 的链接中，没有记录 event2，因为它未在 *`linkTrackEvents`*.

为避免混淆和潜在问题，Adobe建议 *`linkTrackVars`* 在用于链 *`linkTrackEvents`* 接跟踪的链 [!UICONTROL 接的onClick事件中填充] 。

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. 此变量仅在包含“ *`linkTrackVars`* events”时才被考虑。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 转化 | "无" |

## 语法和可能值

The *`linkTrackEvents`*&#x200B;变量是以逗号隔开的事件列表（无空格）。

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

在 *`linkTrackEvents`*. These events are listed in [Events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). 如果事件名称前后出现空格，则此事件不会随任何链接图像请求一起发送。

## 示例

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## 配置设置

无

## 缺陷、问题和提示

* 如果 *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in  only when  is defined.*`linkTrackVars`**`linkTrackEvents`*

* 请注意是否有事件在页面上触发，并在 *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not r