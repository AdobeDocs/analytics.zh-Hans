---
title: getPercentPageViewed
description: 检索访客查看的页面内容所占的百分比。
translation-type: tm+mt
source-git-commit: f11ad012756b5d42b1b53483c8688e30b4b79c83
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 98%

---


# Adobe 插件：getPercentPageViewed

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getPercentPageViewed` 插件可衡量访客的页面滚动活动，以了解访客在进入其他页面前查看了某个页面的多少内容。如果您的页面高度较小或者您不想要测量页面滚动活动，则无需使用此插件。

## 使用 Adobe Experience Platform Launch 扩展安装此插件

Adobe 提供了一个扩展，通过该扩展，您可以使用一些最常用的插件。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]按钮
1. 安装并发布[!UICONTROL 常用 Analytics 插件]扩展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化getPercentPageViewed
1. 保存并发布对上述规则所做的更改。

## 使用 Launch 自定义代码编辑器安装此插件

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
/* Adobe Consulting Plugin: getPercentPageViewed v5.0 w/handlePPVevents helper function (Requires AppMeasurement and the p_fo plugin) */
function getPercentPageViewed(pid,ch){var l=pid,p=ch;function m(){if(window.ppvID){var c=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,k=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,a=Math.min(Math.round(k/c*100),100),n=Math.floor(k/b);b=Math.floor(c/b);var d="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&c!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",k);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");d=window.cookieRead("s_ppv");var f=-1<d.indexOf(",")?d.split(","):[];d=f[0]?f[0]:"";f=f[3]?f[3]:"";var e=window.cookieRead("s_ips");d=d+","+Math.round(f/c*100)+","+Math.round(e/c*100)+","+f+","+n}window.cookieWrite("s_tp",c)}else d=window.cookieRead("s_ppv");var h=d&&-1<d.indexOf(",")?d.split(",",6):[];c=0<h.length?h[0]:escape(window.ppvID);f=1<h.length?parseInt(h[1]):a;e=2<h.length?parseInt(h[2]):a;var l=3<h.length?parseInt(h[3]):k,m=4<h.length?parseInt(h[4]):n;h=5<h.length?parseInt(h[5]):b;0<a&&(d=c+","+(a>f?a:f)+","+e+","+(k>l?k:l)+","+(n>m?n:m)+","+(b>h?b:h));window.cookieWrite("s_ppv",d)}}if("-v"===l)return{plugin:"getPercentPageViewed",version:"5.0"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPercentPageViewed="5.0");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(c,b,a){if("string"===typeof c){var k=window.location.hostname,e=window.location.hostname.split(".").length-1;if(k&&!/^[0-9.]+$/.test(k)){e=2<e?e:2;var d=k.lastIndexOf(".");if(0<=d){for(;0<=d&&1<e;)d=k.lastIndexOf(".",d-1),e--;d=0<d?k.substring(d):k}}g=d;b="undefined"!==typeof b?""+b:"";if(a||""===b)if(""===b&&(a=-60),"number"===typeof a){var f=new Date;f.setTime(f.getTime()+6E4*a)}else f=a;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(a?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),e=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>e?b.length:e)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var a=window.cookieRead("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];l=l?l:window.pageName?window.pageName:document.location.href;a[0]=decodeURIComponent(a[0]);window.ppvChange="undefined"===typeof p||1==p?!0:!1;"undefined"!==typeof e&&e.linkType&&"o"===e.linkType||(window.ppvID&&window.ppvID===l||(window.ppvID=l,window.cookieWrite("s_ppv",""),m()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",m,!1),window.addEventListener("click",m,!1),window.addEventListener("scroll",m,!1)),window._ppvPreviousPage=a[0]?a[0]:"",window._ppvHighestPercentViewed=a[1]?a[1]:"",window._ppvInitialPercentViewed=a[2]?a[2]:"",window._ppvHighestPixelsSeen=a[3]?a[3]:"",window._ppvFoldsSeen=a[4]?a[4]:"",window._ppvFoldsAvailable=a[5]?a[5]:"")};
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

### 5.0（2021年3月19日）

* 已添加版本号作为上下文数据。

### v4.0（2019 年 10 月 7 日）

* 新增了 `s._ppvFoldsSeen` 和 `s._ppvFoldsAvailable` 解决方案

### v3.01（2018 年 8 月 13 日）

* 修复了一个页面上具有多个 AppMeasurement 对象的问题

### v3.0（2018 年 4 月 13 日）

* 修正版本（重新编译，代码更小）
* 此插件现在可创建要分配给 Adobe Analytics 变量而不是返回值的变量
