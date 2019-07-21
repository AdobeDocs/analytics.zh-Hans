---
description: 通过 AJAX 实施的过程与在标准 HTML 页面上部署代码完全一样。
keywords: Analytics 实施
seo-description: 通过 AJAX 实施的过程与在标准 HTML 页面上部署代码完全一样。
seo-title: 进行 AJAX 实施
solution: Analytics
title: 进行 AJAX 实施
topic: 开发人员和实施
uuid: e3477ef-7dea-4c76-ab61-36a188222 be7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 进行 AJAX 实施

通过 AJAX 实施的过程与在标准 HTML 页面上部署代码完全一样。

如果业务中存在需要解决的问题，首先即需要评估该需要并分配变量。然后应用和部署设计。如果您参与过初始阶段的实施，那么对这些概念一定非常熟悉。

## 设计解决方案 {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

进一步进行 [!UICONTROL AJAX] 实施的区别在于，您需要首先了解待收集信息的详细程度。页面内容变化的可能性（宏观级别）以及应用程序的跟踪属性（微观级别）将决定需要设置哪些变量，以及使用哪种方法向 Adobe 发送数据效果最佳。

## 部署代码 {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

JavaScript 代码中有两种函数可允许您发送数据。应当按照一些明确的指导原则确定发送数据时应采用的方法。如果之前已在同一页面上发送图像请求，则必须首先清除先前设置变量的值。Use the `clearVars()` funtion in [!DNL AppMeasurement] for JavaScript, or write a simple JavaScript function to clear the variables if you are using H code. Set the values appropriate for the changed content, namely the *`pageName`* variable. After the variables are set call the *`t()`* function.

>[!NOTE]
>
>Before you call `s.t()`, you must clear any values on the s object that you do not want to persist. if you are using [!DNL AppMeasurement] for JavaScript, you can call `s.clearVars()`. 如果您使用 H 代码，请编写一个简单的例程来将变量设置为空字符串。

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

The following example shows a tracking call in the `done` callback of the JQuery `.ajax` function:

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
* 设置&#x200B;*`linkTrackVars`**`linkTrackEvents`* 变量 [!DNL s_code.js] 。

* Set the values appropriate for the changed content, namely the *`pageName`* variable.
* After the variables are set, call the *`tl()`* function.

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

