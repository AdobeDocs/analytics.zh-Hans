---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkTrackVars

 变量是随自定义、退出和下载链接一起发送的、以逗号隔开的变量列表。

[`linkTrackVars`](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) 参数应包括您想要通过每个文件下载、退出链接和自定义链接跟踪的每个变量。

JS 文件中的 `linkTrackVars` 和 `linkTrackEvents` 设置可影响每个文件下载、退出链接和自定义链接。如果变量（或事件）应用至当前页面而非特定的文件下载、退出链接或自定义链接，则会夸大每个变量和事件的实例。

为确保使用自定义链接代码设置正确的变量，Adobe 建议在自定义链接代码中设置 `linkTrackVars` 和 `linkTrackEvents`，如下所示：

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

在上述示例中，prop1 的值在自定义链接代码中设置。prop2 的值则来自在页面上设置的变量的当前值。

`linkTrackVars` 和 `linkTrackEvents` 的值将覆盖 JS 文件中的设置，并确保仅为特定链接设置自定义链接代码中指定的变量和事件。

*注意：如果`linkTrackVars`（或`linkTrackEvents`）为空（或是诸如 "" 之类的空字符串），则将跟踪为当前页面定义的所有 Analytics 变量（或事件）。换言之，所有具有值的变量都会随链接数据一起发送。这很可能会导致每个变量的实例虚增。为避免与其他变量相关联的实例次数或页面查看次数虚增，Adobe 建议在用于链接跟踪的链接的`linkTrackVars`onClick`linkTrackEvents`事件中填充[!UICONTROL 和]。*

所有应随链接数据（自定义、退出和下载链接）一起发送的变量都应在 `linkTrackVars` 中列出。如果使用 `linkTrackEvents`，则 `linkTrackVars` 应包含“events”。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 任何 | "无" |

填充 `linkTrackVars` 时，请不要使用“s.”作为变量的前缀。例如，不要用“s.prop1”填充 `linkTrackVars`，而应用“prop1”填充。以下示例说明了应如何使用 `linkTrackVars`。

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

由于指向 google.com 的链接为退出链接（除非您就是 Google），event1 和 eVar1 将随退出链接数据一起发送，从而增加与 eVar1 关联的实例以及 event1 的触发次数。在指向 [!DNL test.php] 的链接中，[!UICONTROL eVar1] 随“value C”的某个值一起发送，因为这是在调用 `tl()` 时 eVar1 的当前值。

## 语法和可能值

`linkTrackVars` 变量是以逗号隔开、区分大小写的变量名称列表，无对象名称前缀。使用“eVar1”而不是“s.eVar1”。

```
s.linkTrackVars="variable_name[,variable_name[...]]"
```

`linkTrackVars` 变量只能包含已发送至 [!DNL Analytics] 的变量，即：`events`、`campaign`、`purchaseID`、`products`、`eVar1-75`、`prop1-75`、`hier1-5`、`channel`、`server`、`state`、`zip` 和 `pageType`。

## 示例

```
s.linkTrackVars="events,prop1,eVar49"
```

```
s.linkTrackVars="products"
```

## 配置设置

无

## 缺陷、问题和提示

* 如果 `linkTrackVars` 留为空白，则所有含值的变量将与所有服务器调用一起被跟踪。
* `linkTrackVars` 中列出的任何含值变量，都会在下载、退出或自定义链接时被跟踪。
* 如果使用 `linkTrackEvents`，则 `linkTrackVars` 必须包含“events”。

* 请勿使用“s.”或“s_objectname.”作为变量的前缀。
