---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 82060388a9a2122b66c57725cafa0eb4ce54e147

---


# s.linkTrackEvents

该变量是随自定义、退出或下载链接一起发送的、以逗号隔开的事件列表。The `linkTrackEvents` parameter should include each event you want to track with every file download, exit link, and custom link. 在出现其中一种链接类型时，将跟踪每个已标识变量的当前值。仅当 `linkTrackVars` 包含“events”时，才考虑使用此变量。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 转化 | "无" |

If an event is not in `linkTrackEvents`, it is not sent to Analytics, even if it is populated in the `onClick` event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

The values of [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link. 这两个设置都会影响每个文件下载、退出链接和自定义链接。 如果变量（或事件）应用于当前页面，但不是特定文件下载、退出链接或自定义链接，则每个变量和事件的实例可能会被夸大。

为确保使用自定义链接代码设置正确的变量，Adobe建议按如 *`linkTrackVars`* 下方 *`linkTrackEvents`* 式在自定义链接代码中进行设置：

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

在上例中，prop1的值是在自定义链接代码本身中设置的。 prop2 的值则来自在页面上设置的变量的当前值。

*注意：如果`linkTrackVars`(或`linkTrackEvents`)为null（或空字符串，如“”），则跟踪为当前页面定义的所有Analytics变量（或事件）。 换句话说，所有具有值的变量都会与链接数据一起发送。 这很可能会使每个变量的实例膨胀。 为避免与其他变量相关联的实例次数或页面查看次数虚增，Adobe 建议在用于链接跟踪的链接的`linkTrackVars`onClick`linkTrackEvents`事件中填充[!UICONTROL 和]。*

所有应随链接数据（自定义、退出和下载链接）一起发送的变量都应在 `linkTrackVars`. 如果使用 `linkTrackEvents`，则 `linkTrackVars` 应包含“events”。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 任何 | "无" |

When populating `linkTrackEvents`, do not use the 's.' prefix for variables. 例如，您应该用“event1”填充它，而不是用“s.event1”填充它。 以下示例说明了如何使用它。

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

在第一个链接中，请注意events变量保留在单击链接之前设置的值。 这样可允许 event1 随自定义链接一起发送。In the second example, the link to event2 is not recorded because it is not listed in `linkTrackEvents`.

为避免造成混淆和出现潜在问题，Adobe 建议在用于链接跟踪的链接的 [ 事件中填充 `linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)`linkTrackEvents` 和 `onClick`。

## 语法和可能值

*`linkTrackEvents`* 变量是以逗号隔开的事件列表（无空格）。

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

在 `linkTrackEvents`. 这些事件在[事件](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html)中列出。如果活动名称前后显示空格，则无法随任何链接图像请求一起发送活动。

## 示例

To track `prop1`, `eVar1`, and `event1` with every file download, exit link, and custom link, use the following settings within the global JS file:

```
s.linkTrackVars="prop1,eVar1,events"
```

```
s.linkTrackEvents="event1"
```

**更多示例**

```
s.linkTrackEvents="purchase,event1"
```

```
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## 配置设置

无

## 缺陷、问题和提示

* 如果 `linkTrackEvents` 包含“events”变量，则 JavaScript 文件仅使用 `linkTrackVars`。仅当定义了 `linkTrackVars` 时，“events”才应包含在 `linkTrackEvents` 中。

* 请注意是否有事件在页面上触发，并在 `linkTrackEvents`. 此事件将再次随[!UICONTROL 退出]、[!UICONTROL 下载]或[!UICONTROL 自定义]链接一起记录，除非在该事件之前重置 events 变量（在链接的 [!UICONTROL onClick] 中或调用 `t()` 函数之后）

* 如果 `linkTrackEvents` 的事件名称之间包含空格，则事件将不会被记录。
