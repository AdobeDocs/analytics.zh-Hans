---
title: getTimeBetweenEvents
description: 测量两个事件之间的间隔时间。
feature: Appmeasurement Implementation
exl-id: 15887796-4fe4-4b3a-9a65-a4672c5ecb34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 91%

---

# Adobe 插件：getTimeBetweenEvents

{{plug-in}}

`getTimeBetweenEvents` 插件允许您跟踪任意两个 Analytics 事件（包括购物车事件和自定义事件）之间间隔的时长。此插件可用于跟踪完成结帐流程所需的时间，也可以用于跟踪您想要测量的任何其他流程所需的时间。如果您的任何转化流程都不需要测量所用的时间，则无需使用此插件。

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
   * 操作类型：初始化 getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getTimeBetweenEvents` 函数使用以下参数：

* **`ste`**（必需，字符串）：“启动计时器”事件。由 Analytics“启动计时器”事件构成的以逗号分隔的字符串。
* **`rt`**（必需，布尔）：“重新启动计时器”选项。如果希望每当 `events` 变量包含“启动计时器”事件时便重新启动计时器，则设置为 `true`。如果不希望在遇到“启动计时器”事件时重新启动计时器，则设置为 `false`。
* **`stp`**（必需，字符串）：“停止计时器”事件。由 Analytics“停止计时器”事件构成的以逗号分隔的字符串。
* **`res`**（必需，布尔）：“重置计时器”选项。如果要在计时器启动时开始记录时间，并在计时器停止后重置计时器，则设置为 `true`。如果要记录时间但不停止计时器，则设置为 `false`。如果设置为 `false`，则在 events 变量记录到停止事件后，计时器将继续运行。

  >[!TIP]
  >
  >如果将此参数设置为 `false`，则强烈建议您设置下面的 `rte` 参数。
* **`cn`**（可选，字符串）：存储了首个事件的时间的 Cookie 名称。默认值为 `"s_tbe"`。
* **`etd`**（可选，整数）：Cookie 的过期时间（以天为单位）。如果希望 Cookie 在浏览器会话结束时过期，则设置为 `0`。如果未设置任何值，则将使用默认值，即 1 天。
* **`fmt`**（可选，字符串）：返回秒数时采用的时间格式（默认值为“无”）
   * `"s"` 表示秒
   * `"m"` 表示分钟
   * `"h"` 表示小时
   * `"d"` 表示天
   * 如果未设置，则返回值的格式将遵循以下规则：
      * 若返回值小于 1 分钟，则会以“5 秒”为基准四舍五入到最接近的值。例如：10 秒、15 秒
      * 若返回值介于 1 分钟和 1 小时之间，则会以“0.5 分钟”为基准四舍五入到最接近的值。例如，30.5 分钟、31 分钟
      * 若返回值介于 1 小时和 1 天之间，则会以“0.25 小时”为基准四舍五入到最接近的值。例如，2.25 小时、3.5 小时
      * 若返回值大于 1 天，则会以“1 天”为基准四舍五入到最接近的值。例如，1 天、3 天、9 天
* **`bml`**（可选，数字）：根据 `fmt` 参数的格式，作为四舍五入基准的时长。例如，如果 `fmt` 参数为 `"s"` 且此参数为 `2`，则返回值将以“2 秒”为基准四舍五入到最接近的值。如果 `fmt` 参数为 `"m"` 且此参数为 `0.5`，则返回值将以“0.5 分钟”为基准四舍五入到最接近的值。
* **`rte`**（可选，字符串）：由 Analytics“删除计时器”事件构成的以逗号分隔的字符串。默认值为“无”。

调用此函数将返回一个整数，该整数代表以相应格式表示的“启动计时器”事件与“停止计时器”事件之间间隔的时长。

## 示例调用

```js
// The timer starts or restarts when the events variable contains event1
// The timer stops and resets when the events variable contains event2
// The timer resets when the events variable contains event3 or the visitor closes their browser
// Sets eVar1 to the number of seconds between event1 and event2, rounded to the nearest 2-second benchmark
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");

// The timer starts when the events variable contains event1. It does NOT restart with subsequent hits that also contain event1
// The timer records a "lap" when the events variable contains event2. It does not stop the timer.
// The timer resets when the events variable contains event3 or if more than 20 days pass since the timer started
// The timer is stored in a cookie labeled "s_20"
// Sets eVar4 to the number of hours between event1 and event2, rounded to the nearest 90-minute benchmark
s.eVar4 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");

// Similar to the above timer in eVar4, except the return value is returned in seconds/minutes/hours/days depending on the timer length.
// The timer expires after 1 day.
s.eVar4 = getTimeBetweenEvents("event1", true, "event2", true);
```

## 版本历史记录

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 2.1（2018 年 5 月 26 日）

* 包含对 `formatTime` 插件新版本所做的更改。

### 2.0（2018 年 4 月 6 日）

* 对插件进行了彻底重写/再分析。
