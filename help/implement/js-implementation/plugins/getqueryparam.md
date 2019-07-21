---
description: 返回指定查询字符串参数的值（如果在当前页面 URL 中找到）。由于重要数据（例如促销活动跟踪代码、内部搜索关键词等）可在页面上的查询字符串中找到，getQueryParam 可帮助将这些数据捕获到 Analytics 变量中。
keywords: Analytics 实施
seo-description: 返回指定查询字符串参数的值（如果在当前页面 URL 中找到）。由于重要数据（例如促销活动跟踪代码、内部搜索关键词等）可在页面上的查询字符串中找到，getQueryParam 可帮助将这些数据捕获到 Analytics 变量中。
seo-title: getQueryParam
solution: Analytics
subtopic: 插件
title: getQueryParam
topic: 开发人员和实施
uuid: ba202756-c728-4eBC-8fd9-5bc29 a9 f673 b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getQueryParam

返回指定查询字符串参数的值（如果在当前页面 URL 中找到）。由于重要数据（例如促销活动跟踪代码、内部搜索关键词等）可在页面上的查询字符串中找到，getQueryParam 可帮助将这些数据捕获到 Analytics 变量中。

>[!IMPORTANT]
>
>此插件仅由H代码使用。[AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) 使用 [Util. getQueryParam本机提供此功能](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)。

Once installed in your [!DNL AppMeasurement] for JavaScript code, the plug-in is configured by selecting a [!DNL Analytics] variable to populate using data found in the query string, and specifying which query string values to capture. 该插件会检测是否存在指定的查询字符串；如果存在，将使用该字符串的值填充所选变量。如果未找到具有该值的查询字符串参数，则返回空字符串。If a query string parameter exists but does not have a value (such as param1 in `?param1&param2=value`), the word *`true`* is returned.

>[!NOTE]
>
>The base code for the plug-in must be installed in your [!DNL AppMeasurement] for JavaScript code before the examples below will work.

If you wanted to use *`s.campaign`* to capture campaign tracking codes available as values of the *`cid`* query parameter, you would enter the following in the *`doPlugins()`* function in your [!DNL AppMeasurement] for JavaScript code:

`s.campaign=s.getQueryParam('cid')`

In this example, if the user arrived at a landing page on your site where the URL was [!DNL https://www.yoursite.com/index.html?cid=123456], then *`s.campaign`* would receive a value of *123456*. 可通过 [!DNL DigitalPulse] Debugger 对此进行查看，*v0=123456* 会作为图像请求的一部分显示在该调试程序中。

>[!NOTE]
>
>The parameter *`cid`* and others are used here as examples. 您可以使用您网站上存在的任何查询字符串参数来替换它们。

此&#x200B;*`getQueryParam`*&#x200B;插件具有两个额外的参数（选项），可用于将数据捕获到 Analytics 变量中。

```js
s.getQueryParam('p','d','u') 
 
where: 
p = comma-separated list of query parameters to locate (can also be a single value with no comma) 
d = delimiter for list of values (in case more than one specified parameter is found) 
u = where to search for value (e.g., document.referrer); set to current page URL by default
```

如果 *p* 是一个查询字符串参数列表，且 URL 中找到多个查询字符串参数，则所有值将返回至由分隔符 *d* 分开的列表，分隔符可以是单个字符，也可以是包含多个字符的一个字符串，例如“ : ”（空格-冒号-空格）。如果忽略 *d*，则各值之间不使用分隔符。同时找到两个字符串参数时，如需要优先使用其中的一个，则应使用 *if* 语句，如下所示。

```js
// cid takes precedence over iid if both exist in the query string 
s.campaign=s.getQueryParam('cid'); 
 if(!s.campaign) 
 s.campaign=s.getQueryParam('iid'); 
```

对于&#x200B;*`getQueryParam`* v2.0 及更高版本，该插件接受一个可选的第三个参数 *u*，您可以使用该参数指定要从中提取查询字符串参数的 URL。默认情况下（即，不使用此第三个参数或将其保留为空时），插件会使用页面 URL。例如，如果您要从反向链接中提取查询字符串，则可以使用以下代码：

```js
// take the query string from the referrer 
 s.eVar1=s.getQueryParam('pid','',document.referrer); 
```

在地址栏而不是当前框架 URL 中找到必要的查询字符串参数时，框架中此第三个参数应使用标记“f”。

```js
// take the query string from the parent frame 
 s.eVar1=s.getQueryParam('pid','',f); 
```

使用框架和 *f* 参数时，建议使用&#x200B;*`getValOnce`*&#x200B;插件，以防止在每次页面查看时都发送促销活动跟踪代码。

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

**插件代码**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
 /* Plugin Example: getQueryParam 2.3 
 //single parameter 
 s.campaign=s.getQueryParam('cid'); 
 
 //multiple parameters 
 s.campaign=s.getQueryParam('cid,sid',':'); 
 
 //non-page URL example 
 s.campaign=s.getQueryParam('cid','',document.referrer); 
 
 //parent frame example 
 s.campaign=s.getQueryParam('cid','','f'); 
 
 */ 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 None
```

