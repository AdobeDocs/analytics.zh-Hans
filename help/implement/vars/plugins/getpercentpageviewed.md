---
title: getPercentPageViewed
description: 检索访客查看的页面百分比。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe插件：getPercentPageViewed

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

The `getPercentPageViewed` plug-in measures a visitor&#39;s scroll activity to see how much of a page they view before moving on to another page. 如果您的页面高度较小或不想测量滚动活动，则不必使用此插件。

## 使用Launch自定义代码编辑器安装插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics扩 [!UICONTROL 展下的] “配置”按钮。
1. 使用自定 [!UICONTROL 义代码accordion展开“配置跟踪] ”，该面板显示“打 [!UICONTROL 开编辑器] ”按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存更改并将其发布到Analytics扩展。

## 使用AppMeasurement安装插件

在实例化（使用）Analytics跟踪对象后，复制并粘贴AppMeasurement文件中的任意位置的以下代 `s_gi`码。 在您的实施中保留代码的注释和版本号可帮助Adobe解决任何潜在问题。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getPercentPageViewed` 法使用以下参数：

* **`pid`**（可选，字符串）: 基于页面的标识符，您可以与插件度量提供的百分比相关联。  默认为变`pageName`量。
* **`ch`**（可选，布尔）: 如果您不希`false`望插件在页面初始加载后考虑对页面大小所做的任何更改，请将其设置为(或`0`)。 如果省略，则此参数默认为`true`。 Adobe建议在大多数情况下忽略此参数。

调用此方法不会返回任何内容；而是设置以下变量：

* `s._ppvPreviousPage`:查看的上一页的名称。 加载新页面后，才可使用当前页面的最终滚动度量。
* `s._ppvHighestPercentViewed`：访客查看的上一页面内容所占的最高百分比（以高度衡量）。访客在上一页上向下滚动到的最远点。
* `s._ppvInitialPercentViewed`:上一页首次加载时可见的上一页的百分比。
* `s._ppvHighestPixelsSeen`：访客在上一页面上向下滚动时，所看到的总像素的最大值（以高度衡量）。
* `s._ppvFoldsSeen`:访客向下滚动上一页时“页面折页数”达到最高。 此变量包括“页面顶部”折叠。
* `s._ppvFoldsAvailable`:可在上一页上向下滚动的“页面折页”总数。

将一个或多个这些变量分配给eVar，以在报告中查看维数据。

此插件创建一个名为的第一方Cookie, `s_ppv` 其中包含上述值。 它将在浏览器会话结束时过期。

## 示例调用

### 示例#1

以下代码……

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* 确定是否设置了s.pageName，如果设置了s.pageName，则代码将运行getPercentPageViewed函数
* 当getPercentPageViewed函数运行时，它将创建上面“返回”部分中描述的变量
* 如果“Returns”变量已成功设置：
   * 代码将s.prop1设置为与s._ppvPreviousPage的值（即s.pageName的上一个值或上一页）相等
   * 该代码还将s.prop2设置为上一页的“查看次数最高百分比”和上一页的“查看次数初始百分比”，以及访客到达的折页数和可用的折页数

**注意**: 如果在首次加载时整个页面可见，则“查看的最高百分比”和“查看的初始百分比”尺寸均等于100,“查看的折页”和“可用折页”均等于1。   当整个页面在首次加载时不可见，但访客从未在移到下一页之前向上向下滚动页面，则“查看的最高百分比”和“查看的初始百分比”维度将等于相同的值。

### 示例#2

假设已将 s.prop5 设置为捕获汇总的“页面类型”，而不是整个页面名称。

以下代码确定s.prop5是否已设置，如果已设置，则将其值存储为“上一页”，以与“查看的最高百分比”和“查看的初始百分比”维相关联。  该值仍将存储在s._ppvPreviousPage变量中，但可以视为上一页类型而不是上一页名称。

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## 版本历史

### v4.0（2019年10月7日）

* 新增了 `s._ppvFoldsSeen` 解决方案 `s._ppvFoldsAvailable` 和

### v3.01（2018年8月13日）

* 修复了在页面上具有多个AppMeasurement对象的页面的问题

### v3.0（2018年4月13日）

* 点发行版（重新编译，代码更小）
* 插件现在可创建要分配给Adobe Analytics变量的变量，而不是返回值
