---
title: getPageLoadTime
description: 跟踪页面加载所用的时间。
translation-type: ht
source-git-commit: b3c5fa41194d74725f48e12a546d8ce1c08b9b7d
workflow-type: ht
source-wordcount: '566'
ht-degree: 100%

---


# Adobe 插件：getPageLoadTime

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getPageLoadTime` 插件使用 JavaScript 性能对象来让您可以测量页面完全加载所需的时间。如果您想要测量页面加载所需的时间，Adobe 建议您使用此插件。

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
   * 操作类型：初始化 getPageLoadTime
1. 保存并发布对上述规则所做的更改。

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
/* Adobe Consulting Plugin: getPageLoadTime v2.0 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires AppMeasurement and the p_fo plugin) */
function getPageLoadTime(){function f(){function a(a,b){if(0<=a&&0<=b)return 6E4>a-b&&0<=a-b?parseFloat((a-b)/1E3).toFixed(2):60}var b=performance.timing;0<b.loadEventEnd&&(clearInterval(window.pi),""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",a(b.loadEventEnd,b.navigationStart)),window.cookieWrite("s_pltp",window.pageName)));window.ptc=b.loadEventEnd}if(arguments&&"-v"===arguments[0])return{plugin:"getPageLoadTime",version:"2.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof c&&(c.contextData.getPageLoadTime="2.0");window.pageName="undefined"!==typeof c&&c.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,e){if("string"===typeof a){var c=window.location.hostname,h=window.location.hostname.split(".").length-1;if(c&&!/^[0-9.]+$/.test(c)){h=2<h?h:2;var d=c.lastIndexOf(".");if(0<=d){for(;0<=d&&1<h;)d=c.lastIndexOf(".",d-1),h--;d=0<d?c.substring(d):c}}g=d;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var k=new Date;k.setTime(k.getTime()+6E4*e)}else k=e;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),f=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};"undefined"!==typeof performance&&p_fo("performance")&&((c=performance,c.clearResourceTimings(),""!==window.cookieRead("s_plt")&&(0<c.timing.loadEventEnd&&clearInterval(window.pi),window._pltLoadTime=window.cookieRead("s_plt"),window._pltPreviousPage=window.cookieRead("s_pltp"),window.cookieWrite("s_plt",""),window.cookieWrite("s_pltp","")),0===c.timing.loadEventEnd)?window.pi=setInterval(function(){f()},250):0<c.timing.loadEventEnd&&(window.ptc?window.ptc===c.timing.loadEventEnd&&1===c.getEntries().length&&(window.pwp=setInterval(function(){var a=performance;0<a.getEntries().length&&(window.ppfe===a.getEntries().length?clearInterval(window.pwp):window.ppfe=a.getEntries().length);""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),window.cookieWrite("s_pltp",window.pageName))},500)):f()))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getPageLoadTime` 方法不使用任何参数。调用此方法时，不会返回任何内容。相反，会设置以下变量：

* `s._pltPreviousPage`：上一页，以便您可以将加载时间与上一页关联
* `s._pltLoadTime`：加载上一页所用的时间（以秒为单位）

getPageLoadTime 插件会创建两个第一方 Cookie：

* `s_plt`：加载上一页所用的时间（以秒为单位）。将在浏览器会话结束时过期。
* `s_pltp`：在上一个 Adobe Analytics 图像请求中记录的 `s.pageName` 变量的值。将在浏览器会话结束时过期。

## 示例调用

### 示例 1

运行以下代码...

```js
if(s.pageName) s.getPageLoadTime();
if(s._pltPreviousPage)
{
  s.prop10 = s._pltLoadTime;
  s.prop11 = s._pltPreviousPage
  s.eVar10 = prop11;
  s.events = "event100=" + s._pltLoadTime;
}
```

...将执行以下操作：

* 设置 s.pageName 后运行 getPageLoadTime 插件
* 将 s.prop10 设置为等于上一页的加载时间
* 将 s.prop11 和 s.eVar10 设置为等于上一页的名称（s.pageName 中记录的上一页的名称）
* 将 event100（自定义数值类事件）设置为等于上一页的加载时间。在这种情况下，通过使用自定义事件，可以获得上一页每次加载（来自每位访客/每次访问）累计相加的总时间，从而可以使用计算量度计算出每页面的平均页面加载时间

## 版本历史记录

### 2.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 1.0（2018 年 5 月 22 日）

* 第一版。
