---
description: 在零点几秒内获取页面加载时间，并支持将该值存储在 prop、eVar 和/或数值事件中。
keywords: Analytics 实施
seo-description: 在零点几秒内获取页面加载时间，并支持将该值存储在 prop、eVar 和/或数值事件中。
seo-title: getLoadTime
solution: Analytics
title: getLoadTime
topic: 开发人员和实施
uuid: 5d26a69b-cbde-4be1-bac1-5ee8 a4 e55 ca3
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getLoadTime

在零点几秒内获取页面加载时间，并支持将该值存储在 prop、eVar 和/或数值事件中。

要使用此插件，可以插入函数代码，然后在 [!DNL s_code.js] 文件中调用该函数两次。第一次在文件开头调用，然后在 `doPlugins` 部分再调用一次。此插件有意没有定义为 s 对象的方法。执行此操作可能会增加计算的页面加载时间。

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

## 插件代码和实施 {#section_968AC379C3004C359A85AFED5A48D5AE}

**添加函数**

在 `s_getLoadTime`“DO NOT ALTER ANYTHING BELOW THIS LINE”部分之前的任何位置添加 [!DNL s_code.js] 函数的以下定义：

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**初次调用函数**

Add a call to `s_getLoadTime()` near the beginning of [!DNL s_code.js], outside of any function.

**最后调用函数**

Add another call to `s_getLoadTime()` in the `s_doPlugins()` function, saving the returned value in a prop, eVar, and/or a numeric event.

使用示例 1 - 将页面加载时间保存在 prop10 和 eVar20 中：

```js
s.eVar20=s.prop10=s_getLoadTime();
```

使用示例 2 - 将页面加载时间保存在数值事件 99 中：

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**（可选）添加对较旧浏览器的支持**

要支持不提供 [window.performance.timing](https://www.html5rocks.com/en/tutorials/webperformance/basics/) 属性的较旧浏览器，请将以下行加入页面 HTML 的 HEAD 部分开头附近，同时需要在调用 .js、.css 或其他文件之前完成：

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

