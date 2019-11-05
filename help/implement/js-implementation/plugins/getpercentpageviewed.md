---
description: 衡量访客的页面滚动活动，以了解访客在进入其他页面前查看了某个页面的多少内容。使用此插件可以确定用户查看的内容平均有多少，以便您能够根据用户行为优化页面长度和布局。
keywords: Analytics 实施
seo-description: 衡量访客的页面滚动活动，以了解访客在进入其他页面前查看了某个页面的多少内容。使用此插件可以确定用户查看的内容平均有多少，以便您能够根据用户行为优化页面长度和布局。
seo-title: getPercentPageViewed
solution: Analytics
subtopic: 插件
title: getPercentPageViewed
topic: 开发人员和实施
uuid: 1751dcdb-699f-4bd1-8bcb-5e62fa24896a
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# getPercentPageViewed

getPercentPageViewed 插件可测量访客的滚动活动，以查看访客在转到另一个页面之前已查看的页面内容量。

>[!NOTE]
>如果您的网页高度较小，并且无需测量访客向下滚动的距离，则无需使用 getPercentPageViewed 插件。另外，如果您只想测量退出页面上的滚动活动，则不能使用此插件。

## 先决条件

您必须具有 AppMeasurement 和 handlePPVevents 助手插件才能运行 getPercentPageViewed 插件。

## 实施

要实施此插件，请复制此代码，并将其粘贴到 [!DNL AppMeasurement] 文件中&#x200B;**[!UICONTROL 插件]**&#x200B;部分的任意位置。

>[!NOTE]
>在 AppMeasurement 文件中添加此代码的加粗注释/版本号有助于 Adobe 顾问对任何潜在的实施问题进行故障诊断。

您可以根据需要在 doPlugins 函数中运行 `getPercentPageViewed` 函数（请参阅下面的示例调用。）

## 要传递的参数

| 参数 | 定义 |
|---|---|
| pid（可选，字符串） | 将与插件测量所提供百分比相关联的页码标识符。默认为 Analytics 的 pageName 变量，或者如果未设置 pageName 变量，则默认为 URL |
| ch（可选，布尔值） | 此参数的建议/默认值为“true”。如果您不希望此插件考虑在页面初始加载后对页面大小所做的任何更改（由于 SPA 代码、动态 HTML 等原因），请将此值设为“false”。 |

## 返回结果

getPercentPageViewed 插件不返回任何内容。而是在 AppMeasurement 代码中设置以下变量：

* `s._ppvPreviousPage`：查看的上一页面的名称（因为只有在加载新页面后才能进行最终测量）。
* `s._ppvHighestPercentViewed`：访客查看的上一页面内容所占的最高百分比（以高度衡量）。换句话说，访客在上一页面上向下滚动的最远点。
* `s._ppvInitialPercentViewed`：上一页面首次加载时查看内容所占的百分比。
* `s._ppvHighestPixelSeen`：访客在上一页面上向下滚动时，所看到的总像素的最大值（以高度衡量）。

## Cookie

getPercentPageViewed 插件会创建一个名为 `s_ppv` 的 Cookie，该 Cookie 可在页面之间传递。Cookie 的内容包含上述四个变量中插入的值，并在会话结束时过期。

## 示例调用

**示例调用 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

上述代码示例：
* 确定是否设置了 s.pageName，如果已设置，则代码将运行 getPercentPageViewed 函数。
* 当 `getPercentPageViewed` 函数运行时，它将创建上面“返回”部分中描述的变量。
* 如果成功设置了“Returns”变量：

   * 该代码将 s.prop1 设置为等于 `s._ppvPreviousPag` 的值（即先前的 `s.pageName` 值或上一页面）。
   * 该代码还可将 s.prop2 的值设置为与上一页面的“查看内容所占的最高百分比”和上一页面的“查看内容所占的初始百分比”相等。

>[!NOTE]
>如果整个页面在首次加载时可见，则“查看内容所占的最高百分比”和“查看内容所占的初始百分比”维度都将等于 100。但是，如果整个页面在首次加载时不可见，但是访客在继续浏览下一页之前从不向下滚动页面，则“查看内容所占的最高百分比”和“查看内容所占的初始百分比”维度的值将相同。

**示例调用 2**

假设已将 s.prop5 设置为捕获汇总的“页面类型”，而不是整个页面名称。

以下代码可确定是否已设置 s.prop5，如果已设置，则将其值存储为“上一页”，以与“查看内容所占的最高百分比”和“查看内容所占的初始百分比”维度相关联。尽管该值仍会存储在 `s._ppvPreviousPage` 变量中，但可以将其视为上一个页面类型而不是上一个页面名称。

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## S 对象替换

当使用非“s”的名称实例化主 AppMeasurement 库对象时，请将插件代码的以下部分从以下内容：

`s.getPercentPageViewed=function(pid,ch)`

更改为以下内容：

`[objectname].getPercentPageViewed=function(pid,ch)`

## 要部署的代码

插件区域：将以下代码添加到 `s_code.js` 文件中标记为“PLUGINS SECTION”的区域。请勿对此部分的插件代码进行任何更改。

```
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.01 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); 
pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==
s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window
.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage
=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.01 Plugin) */ 
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```
