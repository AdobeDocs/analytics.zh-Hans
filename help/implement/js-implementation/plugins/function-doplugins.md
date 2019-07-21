---
description: JavaScript 插件通常由 doPlugins 函数调用；在待粘贴代码中调用 t() 函数时，将执行此函数。
keywords: Analytics 实施
seo-description: JavaScript 插件通常由 doPlugins 函数调用；在待粘贴代码中调用 t() 函数时，将执行此函数。
seo-title: doPlugins 函数
solution: Analytics
subtopic: 插件
title: doPlugins 函数
topic: 开发人员和实施
uuid: 367d5550-f8 e2-477d-8681-18ae9665 d699
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# doPlugins 函数

JavaScript 插件通常由 doPlugins 函数调用；在待粘贴代码中调用 t() 函数时，将执行此函数。

因此，如果在 `doPlugins` 函数中设置了一个变量，则可能会覆盖 HTML 页面中设置的某个变量。The only time the `doPlugins` function is not called is when the *`usePlugins`* variable is set to `false`.

**代码示例**

The `doPlugins` function is typically called `s_doPlugins`. 但在特定环境下（通常是在同一页面中显示多个 [!DNL Analytics] 代码版本时），您可以更改 `doPlugins` 函数名称。如果标准 `doPlugins` 函数需重命名以避免冲突，请确保为 `doPlugins` 指定正确的函数名称，如以下示例所示。

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function  
<b>s_mc_doPlugins</b>(s_mc) { 
/* Add calls to plugins here */ 
} 
s_mc.doPlugins= 
<b>s_mc_doPlugins</b>
```

**使用 doPlugins**

该函数可轻松为变量指定默认值，或从任一网站页面的查询字符串参数中获取值。因为只需更新一个文件，因此，在 HTML 页面使用 `doPlugins` 通常比填充值更简单。对 JavaScript 文件的更改并非总是立即生效的。网站的回访者通常会使用缓存版本的 JavaScript 文件。即，在文件更新后多达一个月的时间内，此更新也可能尚未应用到所有访客。

以下示例显示如何使用 `doPlugins` 函数为变量设置默认值，以及从查询字符串获取值的方式。

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
/* Add calls to plugins here */ 
// if prop1 doesn't have a value, set it to "Default Value" 
if(!s.prop1) 
s.prop1="Default Value" 
 
// if campaign doesn't have a value, get cid from the query string 
if(!s.campaign) 
s.campaign=getQueryParam('cid'); 
} 
s.doPlugins=s_doPlugins
```

**安装的插件**

若要确定 JavaScript 文件是否包含插件且准备就绪，可查看 JavaScript 文件中的[!UICONTROL 插件部分]。`getQueryParam` 函数在[!UICONTROL 插件区域]中大致如下所示。

```js
/************************** PLUGINS SECTION *************************/ 
 
/* You may insert any plugins you wish to use here. */ 
/* 
* Plugin: getQueryParam 1.3 - Return query string parameter values 
*/ 
s.getQueryParam=new Function("qp","d","" 
+"vars=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```

