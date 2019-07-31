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
source-git-commit: f9912a0da5930be965e4d249f3d2c1891cfd6ed6

---


# getPercentPageViewed

getPercentpageViewed插件可测量访客的滚动活动，以查看访客在转入另一页之前查看的页面大小。

>[!NOTE]
>如果网页较小并且无需测量访问者向下滚动的距离，则无需使用getPercentPageViewed插件。此外，如果您希望仅测量退出页面上的滚动活动，则无法使用此插件。

## 先决条件

您必须具有AppMeasurement和handlempEvEvents helper插件才能运行getPercentPageViewed插件。

## 实施

To implement this plugin, copy and paste the code to anywhere within the **[!UICONTROL Plugins]** section of the [!DNL AppMeasurement] file.

>[!NOTE]
>向AppMeasurement文件中添加粗体的注释/版本号可帮助Adobe Consulting解决任何潜在实施问题。

You can run the `getPercentPageViewed` function as needed within the doPlugins function (see example calls below.)

## 要传入的参数

| 参数 | 定义 |
|---|---|
| pid(可选，字符串) | 与插件度量所提供的百分比关联的页面标识符。如果未设置pageName变量，它默认为Analytics pageName变量或URL |
| ch(可选，Boolean) | “true”是该参数的建议/默认值。如果您不希望此插件在页面初始加载后考虑对页面大小所做的任何更改(由于SPA代码、动态HTML等)，请将此设置设置为“false”。 |

## 返回结果

getPercentpageViewed插件不返回任何内容。而是在 AppMeasurement 代码中设置以下变量：

* `s._ppvPreviousPage`：查看的上一页的名称(因为在加载新页面之前，最终度量才可用。)
* `s._ppvHighestPercentViewed`：访客查看的上一页的最高百分比(高度)。换句话说，访客在上一页向下滚动的最远点。
* `s._ppvInitialPercentViewed`：上一页首次加载时可见的上一页百分比。
* `s._ppvHighestPixelSeen`：访客向下滚动上一页时显示的最大像素总数(高度)。

## Cookie

The getPercentPageViewed plugin creates a cookie, called `s_ppv`, that is passed from page to page. Cookie的内容包含上述四个变量中插入的值，并在会话结束时过期。

## 调用示例

**示例调用1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

上面的代码示例：
* 确定s. pageName是否已设置，如果是，该代码将运行getPercentpageViewed函数。
* `getPercentPageViewed` 运行函数时，它会创建上面“返回”部分中描述的变量。
* 如果成功设置了“返回”变量：

   * The code sets s.prop1 equal to the value of `s._ppvPreviousPag`e (i.e. the previous value of `s.pageName`, or the previous page.)
   * 该代码还将s. prop设置为上一页查看的最高百分比和上一页查看的初始百分比。

>[!NOTE]
>如果整个页面在首次加载时可见，则查看的最高百分比和初始百分比查看的尺寸将等于100。但是，如果整个页面在首次加载时不可见，但访客在转入下一页之前从不向下滚动页面，则查看的最高百分比和初始百分比查看的尺寸将等于相同的值。

**示例调用2**

假定s. prop被搁置为捕获一个“页面类型”而非整个页面名称。

以下代码确定是否已设置s. prop5，如果是，将其值存储为“上一页”，以与查看的最高百分比和初始百分比查看维度关联。The value is still stored in the `s._ppvPreviousPage` variable but can be treated as if it were the previous page type instead of the previous page name.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## 对象替换

使用除“s”以外的名称实例化主AppMeasurement库对象时，请从以下位置更改插件代码的以下部分：

`s.getPercentPageViewed=function(pid,ch)`

to this：

`[objectname].getPercentPageViewed=function(pid,ch)`

## 部署代码

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
