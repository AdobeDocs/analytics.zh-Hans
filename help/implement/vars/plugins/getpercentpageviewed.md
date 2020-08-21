---
title: getPercentPageViewed
description: 检索访客查看的页面内容所占的百分比。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '798'
ht-degree: 100%

---


# Adobe 插件：getPercentPageViewed

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getPercentPageViewed` 插件可衡量访客的页面滚动活动，以了解访客在进入其他页面前查看了某个页面的多少内容。如果您的页面高度较小或者您不想要测量页面滚动活动，则无需使用此插件。

## 使用 Launch 自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的[!UICONTROL 配置]按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

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

## 使用此插件

`getPercentPageViewed` 方法使用以下参数：

* **`pid`**（可选，字符串）：基于页面的标识符，可将其与此插件测量出的百分比值相关联。默认值为 `pageName` 变量。
* **`ch`**（可选，布尔）：如果您不希望此插件考虑在页面初次加载后对页面大小所做的任何更改，请将该参数设置为 `false`（或 `0`）。如果忽略，则该参数将默认为 `true`。在大多数情况下，Adobe 建议忽略该参数。

调用此方法时，不会返回任何内容；但是，会设置以下变量：

* `s._ppvPreviousPage`：查看的上一个页面的名称。直到新页面加载完成后，才能获得当前页面的最终滚动测量结果。
* `s._ppvHighestPercentViewed`：访客查看的上一页面内容所占的最高百分比（以高度衡量）。访客在上一页面上向下滚动到的最远点。
* `s._ppvInitialPercentViewed`：上一页面首次加载时查看内容所占的百分比。
* `s._ppvHighestPixelsSeen`：访客在上一页面上向下滚动时，所看到的总像素的最大值（以高度衡量）。
* `s._ppvFoldsSeen`：访客在上一页面上向下滚动时，所达到的“页面折叠”的最大值。此变量包括“页面顶部”折叠。
* `s._ppvFoldsAvailable`：在上一页面上向下滚动时，可达到的“页面折叠”总量。

将上述一个或多个变量分配给 eVar，以便在报告中查看维度数据。

此插件会创建一个名为 `s_ppv` 且包含上述值的第一方 Cookie。该 Cookie 将在浏览器会话结束时过期。

## 示例调用

### 示例 1

以下代码...

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* 确定是否设置了 s.pageName，如果已设置，则代码将运行 getPercentPageViewed 函数
* 当 getPercentPageViewed 函数运行时，它将创建上面“Returns”部分中描述的变量
* 如果成功设置了“Returns”变量：
   * 该代码会将 s.prop1 设置为等于 s._ppvPreviousPage 的值（即先前的 s.pageName 值或上一页面）
   * 该代码还会将 s.prop2 设置等于上一页面“查看内容所占的最高百分比”以及上一页面“查看内容所占的初始百分比”，以及访客达到的页面折叠量和可用的页面折叠量。

**注意**：如果在首次加载时整个页面都可见，则“查看内容所占的最高百分比”和“查看内容所占的初始百分比”都等于 100，而“查看的页面折叠量”和“可用的页面折叠量”均等于 1。如果整个页面在首次加载时不可见，但是访客在继续浏览下一页之前从未向下滚动页面，则“查看内容所占的最高百分比”和“查看内容所占的初始百分比”维度的值将相同。

### 示例 2

假设已将 s.prop5 设置为捕获汇总的“页面类型”，而不是整个页面名称。

以下代码可确定是否已设置 s.prop5，如果已设置，则将其值存储为“上一页”，以与“查看内容所占的最高百分比”和“查看内容所占的初始百分比”维度相关联。尽管该值仍会存储在 s._ppvPreviousPage 变量中，但可以将其视为上一个页面类型而不是上一个页面名称。

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## 版本历史记录

### v4.0（2019 年 10 月 7 日）

* 新增了 `s._ppvFoldsSeen` 和 `s._ppvFoldsAvailable` 解决方案

### v3.01（2018 年 8 月 13 日）

* 修复了一个页面上具有多个 AppMeasurement 对象的问题

### v3.0（2018 年 4 月 13 日）

* 修正版本（重新编译，代码更小）
* 此插件现在可创建要分配给 Adobe Analytics 变量而不是返回值的变量
