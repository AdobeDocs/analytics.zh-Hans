---
title: getPercentPageViewed
description: 检索访客查看的页面内容所占的百分比。
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: ht
source-wordcount: '689'
ht-degree: 100%

---

# Adobe 插件：getPercentPageViewed

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getPercentPageViewed` 插件可衡量访客的页面滚动活动，以了解访客在进入其他页面前查看了某个页面的多少内容。如果您的页面高度较小或者您不想要测量页面滚动活动，则无需使用此插件。

## 使用 Adobe Experience Platform 中的标记安装插件

Adobe 提供了一个扩展，通过该扩展，您可以使用一些常用插件。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]按钮
1. 安装并发布[!UICONTROL 常用 Analytics 插件]扩展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化 getPercentPageViewed
1. 保存并发布对上述规则所做的更改。

## 使用自定义代码编辑器安装此插件

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的[!UICONTROL 配置]按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.0.1 */
function getPercentPageViewed(pid,ch){var n=pid,r=ch;function p(){if(window.ppvID){var a=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,d=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,f=Math.min(Math.round(d/a*100),100),l=Math.floor(d/b);b=Math.floor(a/b);var c="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&a!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",d);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");c=window.cookieRead("s_ppv");var h=-1<c.indexOf(",")?c.split(","):[];c=h[0]?h[0]:"";h=h[3]?h[3]:"";var q=window.cookieRead("s_ips");c=c+","+Math.round(h/a*100)+","+Math.round(q/a*100)+","+h+","+l}window.cookieWrite("s_tp",a)}else c=window.cookieRead("s_ppv");var k=c&&-1<c.indexOf(",")?c.split(",",6):[];a=0<k.length?k[0]:encodeURIComponent(window.ppvID);h=1<k.length?parseInt(k[1]):f;q=2<k.length?parseInt(k[2]):f;var t=3<k.length?parseInt(k[3]):d,u=4<k.length?parseInt(k[4]):l;k=5<k.length?parseInt(k[5]):b;0<f&&(c=a+","+(f>h?f:h)+","+q+","+(d>t?d:t)+","+(l>u?l:u)+","+(b>k?b:k));window.cookieWrite("s_ppv",c)}}if("-v"===n)return{plugin:"getPercentPageViewed",version:"5.0.1"};var m=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof m&&(m.contextData.getPercentPageViewed="5.0.1");window.pageName="undefined"!==typeof m&&m.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var f=window.location.hostname,l=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){l=2<l?l:2;var c=f.lastIndexOf(".");if(0<=c){for(;0<=c&&1<l;)c=f.lastIndexOf(".",c-1),l--;c=0<c?f.substring(c):f}}g=c;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),f=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var e=window.cookieRead("s_ppv");e=-1<e.indexOf(",")?e.split(","):[];n=n?n:window.pageName?window.pageName:document.location.href;e[0]=decodeURIComponent(e[0]);window.ppvChange="undefined"===typeof r||1==r?!0:!1;"undefined"!==typeof m&&m.linkType&&"o"===m.linkType||(window.ppvID&&window.ppvID===n||(window.ppvID=n,window.cookieWrite("s_ppv",""),p()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",p,!1),window.addEventListener("click",p,!1),window.addEventListener("scroll",p,!1)),this._ppvPreviousPage=e[0]?e[0]:"",this._ppvHighestPercentViewed=e[1]?e[1]:"",this._ppvInitialPercentViewed=e[2]?e[2]:"",this._ppvHighestPixelsSeen=e[3]?e[3]:"",this._ppvFoldsSeen=e[4]?e[4]:"",this._ppvFoldsAvailable=e[5]?e[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getPercentPageViewed` 函数使用以下参数：

* **`pid`**（可选，字符串）：基于页面的标识符，可将其与此插件测量出的百分比值相关联。默认值为 `pageName` 变量。
* **`ch`**（可选，布尔）：如果您不希望此插件考虑在页面初次加载后对页面大小所做的任何更改，请将该参数设置为 `false`（或 `0`）。如果忽略，则该参数将默认为 `true`。在大多数情况下，Adobe 建议忽略该参数。

调用此函数时，不会返回任何内容；但是，会设置以下变量：

* `s._ppvPreviousPage`：查看的上一个页面的名称。直到新页面加载完成后，才能获得当前页面的最终滚动测量结果。
* `s._ppvHighestPercentViewed`：访客查看的上一页面内容所占的最高百分比（以高度衡量）。访客在上一页面上向下滚动到的最远点。如果整个页面在首次加载时可见，则此值为 `100`。
* `s._ppvInitialPercentViewed`：上一页面首次加载时查看内容所占的百分比。如果整个页面在首次加载时可见，则此值为 `100`。
* `s._ppvHighestPixelsSeen`：访客在上一页面上向下滚动时，所看到的总像素的最大值（以高度衡量）。
* `s._ppvFoldsSeen`：访客在上一页面上向下滚动时，所达到的“页面折叠”的最大值。此变量包括“页面顶部”折叠。如果整个页面在首次加载时可见，则此值为 `1`。
* `s._ppvFoldsAvailable`：在上一页面上向下滚动时，可达到的“页面折叠”总量。如果整个页面在首次加载时可见，则此值为 `1`。

将上述一个或多个变量分配给 eVar，以便在报告中查看维度数据。

此插件会创建一个名为 `s_ppv` 且包含上述值的第一方 Cookie。该 Cookie 将在浏览器会话结束时过期。

## 示例

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the highest percent viewed, the intial percent, the number of folds viewed, and total number of folds of the previous page
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + _ppvHighestPercentViewed + " | initialPercentViewed=" + _ppvInitialPercentViewed + " | foldsSeen=" + _ppvFoldsSeen + " | foldsAvailable=" + _ppvFoldsAvailable;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the highest percent viewed and the initial percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + _ppvHighestPercentViewed + " | initialPercentViewed=" + _ppvInitialPercentViewed;
}
```

## 版本历史记录

### 5.0.1（2021 年 6 月 22 日）

* 修复了某些特殊字符会导致插件崩溃的问题

### 5.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### v4.0（2019 年 10 月 7 日）

* 新增了 `s._ppvFoldsSeen` 和 `s._ppvFoldsAvailable` 解决方案

### v3.01（2018 年 8 月 13 日）

* 修复了一个页面上具有多个 AppMeasurement 对象的问题

### v3.0（2018 年 4 月 13 日）

* 修正版本（重新编译，代码更小）
* 此插件现在可创建要分配给 Adobe Analytics 变量而不是返回值的变量
