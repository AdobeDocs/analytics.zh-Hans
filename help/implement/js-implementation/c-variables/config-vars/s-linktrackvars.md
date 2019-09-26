---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkTrackVars

 变量是随自定义、退出和下载链接一起发送的、以逗号隔开的变量列表。

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. 为避免与其他变量关联的实例或页面查看次数增加，Adobe建议 *`linkTrackVars`* 在用于链 *`linkTrackEvents`* 接跟踪的链 [!UICONTROL 接的onClick] 事件中填充这些变量。

所有应随链接数据（自定义、退出和下载链接）一起发送的变量都应在 *`linkTrackVars`*. 如果 *`linkTrackEvents`* 使用， *`linkTrackVars`* 应包含“events”。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 任何 | "无" |

在填充 *`linkTrackVars`*, do not use the 's.' prefix for variables. 例如，您应该用“ *`linkTrackVars`* prop1”填充它，而不是使用“s.prop1”填充。 The following example illustrates how  should be used.*`linkTrackVars`*

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

由于指向 google.com 的链接为退出链接（除非您就是 Google），event1 和 eVar1 将随退出链接数据一起发送，从而增加与 eVar1 关联的实例以及 event1 的触发次数。In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

## 语法和可能值

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. 使用“eVar1”而不是“s.eVar1”。

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

The  variable may contain only variables that are sent to , namely: , , , , eVar1-75, prop1-75, hier1-5, , , , , and .*`linkTrackVars`*[!DNL Analytics]*`events`**`campaign`**`purchaseID`**`products`**`channel`**`server`**`state`**`zip`**`pageType`*

## 示例

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## 配置设置

无

## 缺陷、问题和提示

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* If  is used,  must contain "events."*`linkTrackEvents`**`linkTrackVars`*

* 请勿使用“s.”或“s_objectname.”作为变量的前缀。