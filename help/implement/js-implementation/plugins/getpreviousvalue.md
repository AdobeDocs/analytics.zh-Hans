---
description: 在下一页面查看时捕获 Analytics 变量值。例如，您可以使用此插件将上一页面查看的 s.pageName 值捕获到一个自定义流量变量中。它还提供一个选项，可以在只有设置了指定的成功事件时才捕获上一个值。
keywords: Analytics 实施
seo-description: 在下一页面查看时捕获 Analytics 变量值。例如，您可以使用此插件将上一页面查看的 s.pageName 值捕获到一个自定义流量变量中。它还提供一个选项，可以在只有设置了指定的成功事件时才捕获上一个值。
seo-title: getPreviousValue
solution: Analytics
subtopic: 插件
title: getPreviousValue
topic: 开发人员和实施
uuid: 20da7b4a-9820-4690-a1 cc-d10 b6 dd627 a7
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPreviousValue

在下一页面查看时捕获 Analytics 变量值。例如，您可以使用此插件将上一页面查看的 s.pageName 值捕获到一个自定义流量变量中。它还提供一个选项，可以在只有设置了指定的成功事件时才捕获上一个值。

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

## 插件代码和实施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**配置区域**：无需对此区域进行任何更改。

**插件配置**

将以下代码置于 *`s_doPlugins()`* 函数，它位于标签为 *`s_code.js`**Plugin Config*&#x200B;的文件区域。选取一个自定义流量 (s.prop) 变量或一个自定义转化 (s.eVar) 变量，以便用于捕获保留值数据。这应该是一个已经通过“管理控制台”启用的变量，且当前未做其他任何使用。您可以使用以下示例并根据需要对它进行更新。

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`*&#x200B;具有三个参数：

1. The variable to be captured from the previous page ( *`s.pageName`* above).
1. The cookie name for use in storing the value for retrieval ( *`gpv_pn`* above).
1. The events that must be set on the page view in order to trigger the retrieval of the previous value ( *`event1`* above). 将其保留为空或忽略时，该插件将捕获所有页面查看的上一个值。

**插件区域**：添加以下代码到 [!DNL s_code.js] 文件中标记为“PLUGINS SECTION”的区域。请勿对此部分的插件代码进行任何更改。

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 
```

**注意**

* 在生产环境中进行部署之前，请务必对插件安装进行广泛地测试，以确保可按预期进行数据收集。
* 如果任意给定页面上的所选变量没有任何值，则将在 Cookie 中设置 *no value*（没有值）文本。
* 现在每个 Cookie 都被设置为固定 30 分钟过期，并会在每次加载页面时刷新。此插件在访问未过期之前有效。
* 由于函数必须放在代码的插件部分进行调用，因此每次调用&#x200B;*`s.t()`* 或被 *`s.tl()`* 调用。

* 必须在调用 *`s.getPreviousValue`*. Because the *`s_doPlugins()`* function is executed after the variables on the page are populated, this issue rarely occurs. It should only be a matter of concern if the variable used with this plug-in is populated within the *`s_doPlugins()`* function and after the call to *`s.getPreviousValue`*.

