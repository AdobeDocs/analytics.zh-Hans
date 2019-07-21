---
description: JavaScript 插件通常由 doPlugins 函数调用；在待粘贴代码中调用 t() 函数时，将执行此函数。
keywords: Analytics 实施
seo-description: JavaScript 插件通常由 doPlugins 函数调用；在待粘贴代码中调用 t() 函数时，将执行此函数。
seo-title: 使用doPlugins函数调用插件
solution: Analytics
subtopic: 插件
title: 使用doPlugins函数调用插件
topic: 开发人员和实施
uuid: 95dd01de-8136-4ec9-aac9-4a3 d5371 b839
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# 使用doPlugins函数调用插件

JavaScript 插件通常由 doPlugins 函数调用；在待粘贴代码中调用 t() 函数时，将执行此函数。

Consequently, if you set a variable in the *`doPlugins`* function, you can overwrite a variable you set on the HTML page. The only time the *`doPlugins`* function is not called is when the [!UICONTROL usePlugins] variable is set to 'false.'

## 代码示例 {#section_6940FD16F2E94753A1C39694D0CF5FBA}

The code example below is what the *`doPlugins`* function looks like in your JavaScript file:

JavaScript AppMeasurement：

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
}
```

H 代码：

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
 /* Add calls to plugins here */ 
} 
s.doPlugins=s_doPlugins
```

>[!NOTE]
>
>H代码及更早版本使用不同的语法支持某些非常旧的浏览器(如IE和5)。

## Renaming the doPlugins Function {#section_70B7D58E057B48058E25907AB3726725}

The *`doPlugins`* function is typically called *`s_doPlugins`*. In certain circumstances, (usually when more than one version of code may appear on a single page) the *`doPlugins`* function name may be changed. If the standard *`doPlugins`* function needs to be renamed to avoid conflicts, ensure that *`doPlugins`* is assigned the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## 使用 doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

*`doPlugins`* 该函数提供了一种简单的方法，可为变量提供默认值，或从站点任何页面 [!UICONTROL 上的查询字符串参数] 中获取值。Using *`doPlugins`* is often easier than populating the values in the HTML page because only one file must be updated. 请记住，对 JavaScript 文件的更改并不总是立即生效。网站的回访者通常会使用缓存版本的 JavaScript 文件。这意味着在更改后最长一个月的时间里，对文件所做的更新可能不会应用于所有访客。

以下示例显示如何使用&#x200B;*`doPlugins`*&#x200B;函数为变量设置默认值，并从查询字符串获取值。

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
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
/* You may insert any plugins you wish to use here.                 */ 
/* 
 * Plugin: getQueryParam 1.3 - Return query string parameter values 
 */ 
s.getQueryParam=new Function("qp","d","" 
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```

