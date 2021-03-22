---
title: getVisitNum
description: 跟踪访客的当前访问数量。
translation-type: tm+mt
source-git-commit: fb1cdcb53732be46037a79587fc2541e629496e3
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 99%

---


# Adobe 插件：getVisitNum

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getVisitNum` 插件可返回在所需天数内访问网站的所有访客所产生的访问数量。Analysis Workspace 提供了一个具有类似功能的维度，即“访问数量”维度。如果您希望提高对访问量递增方式的控制，Adobe 建议您使用此插件。如果 Analysis Workspace 中内置的“访问数量”维度足以满足您的报告需求，则无需使用此插件。

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
   * 操作类型：初始化 getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getVisitNum` 方法使用以下参数：

* **`rp`**（可选，整数或字符串）：访问量计数器重置前的天数。如果未设置此参数，则将默认使用 `365`。
   * 如果将此参数设置为 `"w"`，则计数器将在周末（本周六晚上 11:59）重置
   * 如果将此参数设置为 `"m"`，则计数器将在月末（本月的最后一天）重置
   * 如果将此参数设置为 `"y"`，则计数器将在年末（12 月 31 日）重置
* **`erp`**（可选，布尔）：如果 `rp` 参数是数字，则此参数可确定是否应延长访问量过期时间。如果设置为 `true`，则对您网站的后续点击将重置访问数量计数器。如果设置为 `false`，则当访问数量计数器重置时，对您网站的后续点击将不会延期。默认为 `true`。如果 `rp` 参数为字符串，此参数将无效。

每当访客在处于非活动状态 30 分钟后返回到您的网站时，访问数量便会增加。调用此方法将返回一个表示访客当前访问数量的整数。

此插件将设置一个名为 `"s_vnc[LENGTH]"` 的第一方 Cookie，其中 `[LENGTH]` 为传递到 `rp` 参数的值。例如，`"s_vncw"`、`"s_vncm"` 或 `"s_vnc365"`。该 Cookie 的值包含一个 Unix 时间戳，该时间戳表示访问数量计数器重置的时间，例如周末、月末或处于非活动状态 365 天后。此外，该值还包含当前访问数量。此插件还会设置一个名为 `"s_ivc"` 的 Cookie，该 Cookie 已设为 `true`，且将在处于非活动状态 30 分钟后过期。

## 示例调用

### 示例 1

对于最近 365 天内未访问过网站的访客，以下代码会将 s.prop1 设置为等于 1：

```js
s.prop1=s.getVisitNum();
```

### 示例 2

对于在距首次访问后 364 天内返回到网站的访客，以下代码会将 s.prop1 设置为等于 2：

```js
s.prop1=s.getVisitNum(365);
```

如果该访客在距第二次访问后 364 天内又返回网站，则以下代码会将 s.prop1 设置为等于 3：

```js
s.prop1=s.getVisitNum(365);
```

### 示例 3

对于在距首次访问后 179 天内返回到网站的访客，以下代码会将 s.prop1 设置为等于 2：

```js
s.prop1=s.getVisitNum(180,false);
```

但是，如果该访客在距第二次访问 1 天或更久之后又返回网站，则以下代码会将 s.prop1 设置为等于 1：

```js
s.prop1=s.getVisitNum(180,false);
```

当调用中的第二个参数等于 false 时，用于确定访问量何时应“重置”为 1 的例程将在距访客首次访问网站“x”天（在本示例中为 365 天）后执行此操作。

当第二个参数等于 true（或根本未设置）时，插件将仅在访客处于非活动状态“x”天（在本示例中同样为 365 天）后才会将访问量重置为 1。

### 示例 4

对于在当前周（从星期日开始算起）首次访问网站的所有访客，以下代码会将 s.prop1 设置为等于 1：

```js
s.prop1=s.getVisitNum("w");
```

### 示例 5

对于在当前月份（从每月的第一天开始算起）首次访问网站的所有访客，以下代码会将 s.prop1 设置为等于 1：

```js
s.prop1=s.getVisitNum("m");
```

请记住，getVisitNum 插件不考虑基于零售业的日历（即 4-5-4、4-4-5 等）

### 示例 6

对于在当前年份（从 1 月 1 日开始算起）首次访问网站的所有访客，以下代码会将 s.prop1 设置为等于 1：

```js
s.prop1=s.getVisitNum("y");
```

### 示例 7

如果您希望跟踪访客在某周、某月和某年的访问数量，而所有这些都在不同的 Analytics 变量中，则应使用类似于以下代码的代码：

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

在这种情况下，此插件将创建三个不同的 Cookie（为三个不同时间段各创建一个 Cookie），以分别跟踪每个时间段的访问量。

## 版本历史记录

### 4.2（2021年3月19日）

* 已添加版本号作为上下文数据。

### 4.11（2019 年 9 月 30 日）

* 修复了明确将 `erp` 参数设置为 `false` 的问题。

### 4.1（2018 年 5 月 21 日）

* 已将 `endOfDatePeriod` 插件更新为 v1.1。

### 4.0（2018 年 4 月 17 日）

* 修正版本（重新编译，代码更小）。
* 删除了 Cookie 参数，因为插件现在会根据 `rp` 参数动态生成 Cookie

### 3.0（2016 年 6 月 5 日）

* 全面检修
* 整合了所有以往在各个版本的 `getVisitNum` 插件中可用的解决方案。
