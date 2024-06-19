---
title: getPercentPageViewed
description: 检索访客查看的页面内容所占的百分比。
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 84%

---

# Adobe 插件：getPercentPageViewed

{{plug-in}}

`getPercentPageViewed` 插件可衡量访客的页面滚动活动，以了解访客在进入其他页面前查看了某个页面的多少内容。如果您的页面高度较小或者您不想要测量页面滚动活动，则无需使用此插件。

## 使用Web SDK或Web SDK扩展安装此插件

尚不支持使用此插件在Web SDK中使用。

## 使用Adobe Analytics扩展安装此插件

Adobe提供了一个扩展，通过该扩展，您可以将最常用的插件与Adobe Analytics结合使用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
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

如果您不想使用“常用Analytics插件”插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getPercentPageViewed` 函数使用以下参数：

* **`pid`**（可选，字符串）：等于当前页面的变量或值。默认为 Analytics AppMeasurement `pageName` 变量或当前 URL（如果未设置 AppMeasurement pageName 变量）。
* **`ch`**（可选，布尔）：如果您不希望此插件考虑在页面初次加载后对页面大小所做的任何更改，请将该参数设置为 `false`（或 `0`）。如果忽略，则该参数将默认为 `true`。在大多数情况下，Adobe 建议忽略该参数。

调用此函数时，不会返回任何内容；但是，会设置以下变量：

* `window._ppvPreviousPage`：查看的上一个页面的名称。直到新页面加载完成后，才能获得当前页面的最终滚动测量结果。
* `window._ppvInitialPercentViewed`：上一页面首次加载时查看内容所占的百分比。如果整个页面在首次加载时可见，则此值为 `100`。
* `window._ppvHighestPercentViewed`：访客查看的上一页面内容所占的最高百分比（以高度衡量）。访客在上一页面上向下滚动到的最远点。如果整个页面在首次加载时可见，则此值为 `100`。
* `window._ppvFinalPercentViewed`：在访客移至当前页面上时，上一页的可见内容的百分比。该值将大于或等于已查看内容的初始百分比，也将等于或小于已查看页面内容的最高百分比。
* `window._ppvHighestPixelsSeen`：访客在上一页面上向下滚动时，所看到的总像素的最大值（以高度衡量）。
* `window._ppvFoldsAvailable`：在上一页面上向下滚动时，可达到的“页面折叠”总量。如果整个页面在首次加载时可见，则此值为 `1`。
* `window._ppvFoldsSeen`：访客在上一页面上向下滚动时，所达到的“页面折叠”的最大值。此变量包括“页面顶部”折叠。如果整个页面在首次加载时可见，则此值为 `1`。

将上述一个或多个变量分配给 eVar，以便在报告中查看维度数据。

此插件会创建三个第一方Cookie，它们将在浏览器会话结束时过期：

* `s_ppv`：存储通过调用函数公开的每个值
* `s_tp`：存储上一页的总像素高度
* `s_ips`：存储上一页的初始滚动百分比

## 示例

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the intial percent, the highest percent, and the final percent viewed; the number of folds available on the page, and the number of folds viewed ( of the previous page)
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## 版本历史记录

### 5.1（2022 年 12 月 8 日）

* 添加了 `_finalPercentViewed` 解决方案

### 5.0.1（2021 年 6 月 22 日）

* 修复了某些特殊字符会导致插件中断的问题

### 5.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### v4.0（2019 年 10 月 7 日）

* 新增了 `s._ppvFoldsSeen` 和 `s._ppvFoldsAvailable` 解决方案

### v3.01（2018 年 8 月 13 日）

* 修复了一个页面上具有多个 AppMeasurement 对象的问题

### v3.0（2018 年 4 月 13 日）

* 修正版本（重新编译，代码更小）
* 此插件现在可创建要分配给 Adobe Analytics 变量而不是返回值的变量
