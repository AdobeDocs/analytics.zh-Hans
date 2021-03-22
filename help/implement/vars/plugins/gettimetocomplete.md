---
title: getTimeToComplete
description: 测量完成一项任务所需的时间。
translation-type: tm+mt
source-git-commit: 37a3a44053260d9cdb2a3797e07f6d34592abc1f
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 99%

---


# Adobe 插件：getTimeToComplete

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getTimeToComplete` 插件可跟踪用户在网站上完成某个流程所需的时间。“时钟”在调用 `start` 操作时开始，并在调用 `stop` 操作时结束。如果网站上的某个工作流程需要花一些时间才能完成，并且您希望了解访客完成该工作流程所用的时间，Adobe 建议使用此插件。如果网站上的工作流程需要很短时间（少于 3 秒）即可完成，则无需使用此插件，因为可测量的最小时间粒度为 1 秒。

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
   * 操作类型：初始化 getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v4.0 */
function getTimeToComplete(sos,cn,exp,tp){var f=sos,m=cn,l=exp,e=tp;if("-v"===f)return{plugin:"getTimeToComplete",version:"4.0"};var k=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof k&&(k.contextData.getTimeToComplete="4.0");window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var h="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,h="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,h="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,h="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,h="seconds",d=isNaN(d)?.2:b/d);h=Math.round(c*d/b)/d+" "+h;0===h.indexOf("1 ")&&(h=h.substring(0,h.length-1));return h}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var e=window.location.hostname,h=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){h=2<h?h:2;var f=e.lastIndexOf(".");if(0<=f){for(;0<=f&&1<h;)f=e.lastIndexOf(".",f-1),h--;f=0<f?e.substring(f):e}}g=f;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""};f=f?f.toLowerCase():"start";if("stop"===f||"start"===f){m=m?m:"s_gttc";e?e="d"===e?864E5:"h"===e?36E5:"s"===e?1E3:6E4:(l=30,e=6E4);l=isNaN(l)?30:l;l*=e;k=cookieRead(m);e=new Date;if("stop"===f&&k)return l=Math.round((e.getTime()-k)/1E3),cookieWrite(m,"",0),formatTime(l);"start"!==f||k?k&&Number(k)<e.getTime()+18E5&&cookieWrite(m,k,30):(f=String(e.getTime()),e.setTime(e.getTime()+l),cookieWrite(m,f,e))}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getTimeToComplete` 方法使用以下参数：

* **`sos`**（可选，字符串）：要启动计时器时设置为 `"start"`。要停止计时器时设置为 `"stop"`。默认为 `"start"`。
* **`cn`**（可选，字符串）：用于存储开始时间的 Cookie 的名称。默认为 `"s_gttc"`。
* **`exp`**（可选，整数）：Cookie（和计时器）的过期时间（以天为单位）。默认值为 `0`，表示将在浏览器会话结束时过期。

调用此方法将返回一个字符串，其中包含从 `"start"` 操作到 `"stop"` 操作所用的时间（天数、小时数、分钟数和/或秒数）。

## 示例调用

### 示例 1

使用此类调用可确定从访客开始进入结帐流程到完成购买所用的时间。

访客开始结帐时启动计时器：

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

当访客完成购买时停止计时器，并将 prop1 设置为停止时间与开始时间之间的时间差：

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 将捕获完成购买流程所需的时间

### 示例 2

如果要同时运行多个定时器（以测量不同的进程），您需要手动设置 cn Cookie 参数。例如，如果要测量完成购买所需的时间，您应设置以下代码...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...但是，如果您还想同时测量填写注册表单所需的时间，您还应运行以下代码：

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

在第二个示例中，event1 用于捕获注册流程（由于某些原因，可能需要长达 7 天时间才能完成）的开始，event2 用于捕获注册流程的结束。s.prop2 将捕获完成注册流程所需的时间

## 版本历史记录

### 4.0（2021年3月19日）

* 已添加版本号作为上下文数据。

### 3.1（2019 年 9 月 30 日）

* 添加了要求第一个参数中的值只能为“start”或“stop”的逻辑。传入的所有其他值都会阻止插件运行。
* 已将 `inList 2.0` 插件更新为 `inList 2.1`。

### 3.0（2018 年 8 月 23 日）

* 已将 `formatTime v1.0` 插件更新为 `formatTime v1.1`。

### 3.0（2018 年 4 月 17 日）

* 修正版本（重新编译，代码更小）。
* 若干小错误修复。

### 2.0（2016 年 6 月 21 日）

* 消除了对 `p_fo` 插件的依赖性。
* 增加了与 H 代码和 AppMeasurement 的兼容性。
* 添加了控制台日志记录。
