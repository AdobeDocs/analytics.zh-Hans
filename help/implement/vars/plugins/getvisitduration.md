---
title: getVisitDuration
description: 跟踪访客在网站上停留的时间。
feature: Variables
exl-id: 5299caa8-1e47-40b0-a8f4-422590f33ee4
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 70%

---

# Adobe 插件：getVisitDuration

{{plug-in}}

`getVisitDuration` 插件可跟踪访客在某个时间点之前在网站上停留的时间（以分钟为单位）。如果您希望跟踪截至某个时间点为止访客在网站上停留的总时间，或跟踪访客执行某项活动所用的时间，Adobe 建议您使用此插件。此插件不会跟踪事件之间的间隔时间；如果需要使用此功能，请使用 [`getTimeBetweenEvents`](gettimebetweenevents.md) 插件。

## 使用Web SDK扩展安装此插件

Adobe提供了一个扩展，通过该扩展，您可以将最常用的插件与Web SDK结合使用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击左侧的&#x200B;**[!UICONTROL 标记]**，然后单击所需的标记属性。
1. 单击左侧的&#x200B;**[!UICONTROL 扩展]**，然后单击&#x200B;**[!UICONTROL 目录]**&#x200B;选项卡
1. 找到并安装&#x200B;**[!UICONTROL 常用Web SDK插件]**&#x200B;扩展。
1. 单击左侧的&#x200B;**[!UICONTROL 数据元素]**，然后单击所需的数据元素。
1. 使用以下配置设置所需的数据元素名称：
   * 扩展：常用Web SDK插件
   * 数据元素： `getVisitDuration`
1. 保存并发布对数据元素所做的更改。

## 安装插件以手动实施Web SDK

尚不支持在手动实施Web SDK时使用此插件。

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
   * 操作类型：初始化 getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.1 */
function getVisitDuration(){if(arguments&&"-v"===arguments[0])return{plugin:"getVisitDuration",version:"2.1"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getVisitDuration="2.1");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};d=(new Date).getTime();var k=cookieRead("s_dur"),a=0;if(isNaN(k)||18E5<d-k)k=d;a=d-k;cookieWrite("s_dur",k+"",30);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute":a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getVisitDuration` 函数不使用任何参数。它会返回以下任一值：

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"`（其中 `[x]` 是自访客登录网站后所经过的时间，以分钟为单位）

此插件将创建一个名为 `"s_dur"` 的第一方 Cookie，用于记录自访客登录网站起所经过的时间（以毫秒为单位）。该 Cookie 将在处于非活动状态 30 分钟后过期。

## 示例

```js
// Always sets eVar10 to the number of minutes passed since the visitor first landed on the site
s.eVar10 = getVisitDuration();

// Checks if the events variable contains the purchase event.
// If it does, sets eVar56 to the number of minutes between the start of the visit and the time of purchase
if(inList(s.events, "purchase")) s.eVar56 = getVisitDuration();
```

## 版本历史记录

### 2.1（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 2.0（2018 年 5 月 2 日）

* 修正版本（对插件进行了彻底再分析/重写）。
