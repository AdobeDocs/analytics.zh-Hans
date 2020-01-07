---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: ca0797a353661a72d4064aa5aa84c3d9b7eb38a5

---


# s.linkTrackEvents

该变量是随自定义、退出或下载链接一起发送的、以逗号隔开的事件列表。`linkTrackEvents` 参数应包括您想要通过每个文件下载、退出链接和自定义链接跟踪的每个事件。在出现其中一种链接类型时，将跟踪每个已标识变量的当前值。仅当 [`linkTrackVars`](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) 包含“events”时，才考虑使用此变量。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 转化 | "无" |

如果某个事件不在 `linkTrackEvents` 中，即使它是在链接的 `onClick` 事件中填充的，该事件也不会发送到 Analytics，如以下示例所示：

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

[`linkTrackVars`](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) 和 `linkTrackEvents` 的值将覆盖 JS 文件中的设置，并确保仅为特定链接设置自定义链接代码中指定的变量和事件。这两个设置都可以影响每个文件下载、退出链接和自定义链接。如果变量（或事件）应用至当前页面而非特定的文件下载、退出链接或自定义链接，则会夸大每个变量和事件的实例。

要确保使用自定义链接代码设置正确的变量，Adobe 建议在自定义链接代码中设置 *`linkTrackVars`* 和 *`linkTrackEvents`*，如下所示：

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

在上述示例中，`prop1` 的值在自定义链接代码中设置。`prop2` 的值则来自在页面上设置的变量的当前值。

*注意：如果`linkTrackVars`（或`linkTrackEvents`）为空（或是诸如 "" 之类的空字符串），则将跟踪为当前页面定义的所有 Analytics 变量（或事件）。换言之，所有具有值的变量都会随链接数据一起发送。这很可能会导致每个变量的实例虚增。为避免与其他变量相关联的实例次数或页面查看次数虚增，Adobe 建议在用于链接跟踪的链接的`linkTrackVars`事件中填充`linkTrackEvents`和`onClick`。*

所有应随链接数据（自定义、退出和下载链接）一起发送的变量都应在 `linkTrackVars` 中列出。如果使用 `linkTrackEvents`，则 `linkTrackVars` 应包含“events”。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 任何 | "无" |

填充 `linkTrackEvents` 时，请不要使用“s.”作为变量的前缀。例如，填充时，您应使用“event1”而不是“s.event1”。以下示例说明了应如何使用该变量。

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

在第一个链接中，注意事件变量保留了在点击链接前设置的值。这样可允许 `event1` 随自定义链接一起发送。在第二个示例，指向 `event2` 的链接未记录，因为它未在 `linkTrackEvents` 中列出。

为避免造成混淆和出现潜在问题，Adobe 建议在用于链接跟踪的链接的 [ 事件中填充 `linkTrackVars`](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)`linkTrackEvents` 和 `onClick`。

## 语法和可能值

*`linkTrackEvents`* 变量是以逗号隔开的事件列表（无空格）。

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

`linkTrackEvents` 中仅允许使用事件名称。这些事件在[事件](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/analytics-basics/ref-events.html)中列出。如果事件名称前后出现空格，则此事件不会随任何链接图像请求一起发送。

## 示例

若要通过每个文件下载、退出链接和自定义链接跟踪 `prop1`、`eVar1` 和 `event1`，可在全局 JS 文件中使用以下设置：

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

* 请注意是否有事件在页面上触发，并在 `linkTrackEvents` 中列出。此事件将再次随退出、下载或自定义链接一起记录，除非在该事件之前重置 events 变量（在链接的 `onClick` 中或调用 `t()` 函数之后）

* 如果 `linkTrackEvents` 的事件名称之间包含空格，则事件将不会被记录。
