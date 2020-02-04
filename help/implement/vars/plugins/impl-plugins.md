---
description: AppMeasurement for JavaScript 插件是执行多项高级功能的程序或功能。
keywords: Analytics Implementation
subtopic: Plug-ins
title: 使用实施插件
topic: Developer and implementation
uuid: 7ffcfe89-b7e2-45e4-b771-942d5ae07c39
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# 使用实施插件

插件是执行多个高级功能以帮助您实施Analytics的代码片段。

这些插件扩展了 JavaScript 文件的功能，提供了多项基本实施所没有的功能。作为高级解决方案的一部分，Adobe 提供了许多其他插件。如果您希望使用 JavaScript 捕获数据，但又不确定从何处入手，请联系您的客户经理。

JavaScript plug-ins are usually called by the doPlugins function, which is executed when the `t` method is called in the Code to Paste.

因此，如果在 *`doPlugins`*函数中设置了一个变量，则可能会覆盖 HTML 页面中设置的某个变量。唯一不调用*`doPlugins`* 函数的时候，是在 [!UICONTROL usePlugins] 变量设置为“false”时。

## 代码示例 {#section_6940FD16F2E94753A1C39694D0CF5FBA}

以下代码示例展示了 *`doPlugins`*函数在 JavaScript 文件中的样子：

AppMeasurement for JavaScript:

```js
/* Plugin Config */
s.usePlugins=true
s.doPlugins=function(s) {
 /* Add calls to plug-ins here */
}
```

H 代码：

```js
/* Plugin Config */
s.usePlugins=true
function s_doPlugins(s) {
 /* Add calls to plug-ins here */
}
s.doPlugins=s_doPlugins
```

> [!NOTE]H 代码及之前的版本使用不同的语法来支持某些非常旧的浏览器（如 IE 4 和 5）。

## 重命名 doPlugins 函数 {#section_70B7D58E057B48058E25907AB3726725}

*`doPlugins`*函数通常被称为*`s_doPlugins`*。在特定情况下（通常是在同一页面中显示多个代码版本时），*`doPlugins`*函数名称可能会被更改。如果标准*`doPlugins`* 函数需重命名以避免冲突，请确保为 *`doPlugins`*指定正确的函数名称，如以下示例所示。

```js
/* Plugin Config */
s_mc.usePlugins=true
function s_mc_doPlugins(s_mc) {
 /* Add calls to plug-ins here */
}
s_mc.doPlugins=s_mc_doPlugins
```

## 使用 doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

*`doPlugins`*函数可轻松为变量指定默认值，或从任一网站页面的[!UICONTROL 查询字符串参数]中获取值。因为只需更新一个文件，因此，在 HTML 页面使用*`doPlugins`* 通常比在 HTML 页面中填充值更加简单。请记住，对 JavaScript 文件的更改并不总是立即生效。网站的回访者通常会使用缓存版本的 JavaScript 文件。这意味着在更改后最长一个月的时间里，对文件所做的更新可能不会应用于所有访客。

以下示例显示如何使用&#x200B;*`doPlugins`*函数为变量设置默认值，并从查询字符串获取值。

```js
/* Plugin Config */
s.usePlugins=true
s.doPlugins=function(s) {
 /* Add calls to plug-ins here */
 // if prop1 doesn't have a value, set it to "Default Value"
 if(!s.prop1)
s.prop1="Default Value"

 // if campaign doesn't have a value, get cid from the query string
 if(!s.campaign)
s.campaign=s.getQueryParam('cid');

// Note: The code to read query parameters is different for
// Appmeasurement for JavaScript since a plug-in is not required:
// s.campaign=s.Util.getQueryParam('cid');
}
```

## 安装的插件 {#section_C5494347D85940A78670032199787CD0}

若要确定 JavaScript 文件是否包含插件且能够使用，可查看 JavaScript 文件中的[!UICONTROL 插件区域]。以下示例显示了 [!UICONTROL getQueryParam] 函数。

```js
/************************** PLUGINS SECTION *************************/
/* You may insert any plug-ins you wish to use here.                 */
/*
 * Plugin: getQueryParam 1.3 - Return query string parameter values
 */
s.getQueryParam=new Function("qp","d",""
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l"
//
// ... more code below ...
//
```

