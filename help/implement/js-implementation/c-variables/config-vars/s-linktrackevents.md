---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkTrackEvents

该变量是随[!UICONTROL 自定义]、[!UICONTROL 退出]或[!UICONTROL 下载]链接一起发送的、以逗号隔开的事件列表。

如果某个事件不在 *`linkTrackEvents`* 中，则此事件不会发送到 [!DNL Analytics]，即使它是在链接的 [!UICONTROL onClick] 事件中填充的，如以下示例所示。

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

在指向 [!DNL help.php] 的第一个链接中，注意事件变量保留了在点击链接前设置的值，这样可允许 event1 随自定义链接一起发送。在第二个示例，即指向 [!DNL test.php] 的链接中，没有记录 event2，因为它未在 *`linkTrackEvents`*.

为避免造成混淆和出现潜在问题，Adobe 建议在用于链接跟踪的链接的 [!UICONTROL onClick] 事件中填充 *`linkTrackVars`* 和 *`linkTrackEvents`*。

*`linkTrackEvents`* 变量包含应当随[!UICONTROL 自定义]、[!UICONTROL 下载]和[!UICONTROL 退出]链接一起发送的事件。仅当 *`linkTrackVars`* 包含“events”时，才考虑使用此变量。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 转化 | "无" |

## 语法和可能值

*`linkTrackEvents`* 变量是以逗号隔开的事件列表（无空格）。

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

在 *`linkTrackEvents`*. 这些事件在[事件](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html)中列出。如果事件名称前后出现空格，则此事件不会随任何链接图像请求一起发送。

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

* 如果 *`linkTrackVars`* 包含“events”变量，则 JavaScript 文件仅使用 *`linkTrackEvents`*。仅当定义了 *`linkTrackEvents`* 时，“events”才应包含在 *`linkTrackVars`* 中。

* 请注意是否有事件在页面上触发，并在 *`linkTrackEvents`*. 此事件将再次随[!UICONTROL 退出]、[!UICONTROL 下载]或[!UICONTROL 自定义]链接一起记录，除非在该事件之前重置 events 变量（在链接的 [!UICONTROL onClick] 中或调用 *`t()`* 函数之后）

* 如果 *`linkTrackEvents`* 的事件名称之间包含空格，则事件将不会被记录。
