---
description: 通过 AJAX 实施的过程与在标准 HTML 页面上部署代码完全一样。
keywords: Analytics Implementation
solution: Analytics
title: 使用 AJAX 实施
topic: Developer and implementation
uuid: 9e3477ef-7dea-4c76-ab61-36a188222be7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 使用 AJAX 实施

通过 AJAX 实施的过程与在标准 HTML 页面上部署代码完全一样。

如果业务中存在需要解决的问题，首先即需要评估该需要并分配变量。然后应用和部署设计。如果您参与过初始阶段的实施，那么对这些概念一定非常熟悉。

## 设计解决方案 {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

进一步进行 [!UICONTROL AJAX] 实施的区别在于，您需要首先了解待收集信息的详细程度。页面内容变化的可能性（宏观级别）以及应用程序的跟踪属性（微观级别）将决定需要设置哪些变量，以及使用哪种方法向 Adobe 发送数据效果最佳。

## 部署代码 {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

JavaScript 代码中有两种函数可允许您发送数据。应当按照一些明确的指导原则确定发送数据时应采用的方法。如果之前已在同一页面上发送图像请求，则必须首先清除先前设置变量的值。如果您使用 H 代码，则使用 [!DNL AppMeasurement] for JavaScript 中的 `clearVars()` 函数，或者编写一个简单的 JavaScript 函数来清除变量。为更改后的内容设置适当的值，即 *`pageName`* 变量。在变量设置完成之后调用 *`t()`* 函数。

> [!NOTE]调用 `s.t()` 之前，必须清除 s 对象上所有您不希望再保存的值。如果您使用 [!DNL AppMeasurement] for JavaScript，则可以调用 `s.clearVars()`。如果您使用 H 代码，请编写一个简单的例程来将变量设置为空字符串。

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

下面的示例显示了 JQuery `done` 函数的 `.ajax` 回调中的一个跟踪调用：

```
$.ajax({ 
  url: "test.html", 
  dataType: "html" 
}) 
  .done(function( response ) { 
    $( "#content" ).html( response ); 
  s.clearVars(); 
  s.pageName = $( "h1:first" ).text(); 
  s.t(); 
  }); 
```

如果之前已在同一页面上发送图像请求，则可以首先清除先前设置的变量值。这可通过以下几种方式来完成：

* 写入一个简单的 JavaScript 函数来清除 Adobe 变量。
* 设置 *`linkTrackVars`* 和 *`linkTrackEvents`* 变量（如果您尚未在 [!DNL s_code.js] 文件中完成此设置）。

* 为更改后的内容设置适当的值，即 *`pageName`* 变量。
* 在变量设置完成之后调用 *`tl()`* 函数。

```js
//set linkTrackVars and linkTrackEvents> (if applicable) 
//set new variables 
s.tl(this,'o','Link Name');
```

```js
s.linkTrackVars="prop1,eVar1,events"; s.linkTrackEvents="event1"; 
s.prop1="some value"; s.eVar1="another value"; s.events="event1"; 
s.tl(this,'o','My Link Name');
```

