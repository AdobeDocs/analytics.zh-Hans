---
title: getTimeBetweenEvents
description: 测量两个事件之间的间隔时间。
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 100%

---


# Adobe 插件：getTimeBetweenEvents

>[!IMPORTANT]
>
> 此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getTimeBetweenEvents` 插件允许您跟踪任意两个 Analytics 事件（包括购物车事件和自定义事件）之间间隔的时长。此插件可用于跟踪完成结帐流程所需的时间，也可以用于跟踪您想要测量的任何其他流程所需的时间。如果您的任何转化流程都不需要测量所用的时间，则无需使用此插件。

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
   * 操作类型：初始化 getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getTimeBetweenEvents` 方法使用以下参数：

* **`ste`**（必需，字符串）：“启动计时器”事件。由 Analytics“启动计时器”事件构成的以逗号分隔的字符串。
* **`rt`**（必需，布尔）：“重新启动计时器”选项。如果希望每当 `events` 变量包含“启动计时器”事件时便重新启动计时器，则设置为 `true`。如果不希望在遇到“启动计时器”事件时重新启动计时器，则设置为 `false`。
* **`stp`**（必需，字符串）：“停止计时器”事件。由 Analytics“停止计时器”事件构成的以逗号分隔的字符串。
* **`res`**（必需，布尔）：“重置计时器”选项。如果要在计时器启动时开始记录时间，并在计时器停止后重置计时器，则设置为 `true`。如果要记录时间但不停止计时器，则设置为 `false`。如果设置为 `false`，则在 events 变量记录到停止事件后，计时器将继续运行。
   >[!TIP] 如果将此参数设置为 `false`，则强烈建议您设置下面的 `rte` 参数。
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

调用此方法将返回一个整数，该整数代表以相应格式表示的“启动计时器”事件与“停止计时器”事件之间间隔的时长。

## 示例调用

### 示例 1

以下代码...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...配置为按如下方式行事：

* 当 s.events 中包含 event1 时，计时器将启动。
* 每当 s.events 中包含 event1 时，计时器便将重新启动
* 当 s.events 中包含 event2 时，计时器将停止
* 每当 s.events 中包含 event2 时，计时器便将重置（即变为 0 秒）
* 当 s.events 中包含 event3 或访客关闭其浏览器时，计时器也会重置
* 如果记录了 event1 和 event2 之间的实际间隔时间，此插件会将 eVar1 设置为等于这两个事件的设置时间所间隔的秒数（此秒数会以“2 秒”为基准四舍五入到最接近的值，例如 0 秒、2 秒、4 秒、10 秒、184 秒等）
* 如果 s.events 在计时器启动之前包含 event2，则根本不会设置 eVar1。

### 示例 2

以下代码...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...配置为按如下方式行事：

* 当 s.events 中包含 event1 时，计时器将启动。
* 计时器不会在每当 s.events 包含 event1 时便重新启动一次，而是第一个计时器将一直运行
* 当 s.events 中包含 event2 时，计时器将不会停止，但此插件将记录自记录原始 event1 设置以来的时间
* 计时器存储在名为“s_20”的 Cookie 中
* 仅当 s.events 中包含 event3 时或者自计时器启动直已经过 20 天时，计时器才会重置
* 如果记录了 event1（原始事件）和 event2 之间的间隔时间，此插件会将 eVar1 设置为等于这两个事件的设置时间所间隔的小时数（此小时数会以“0.5”小时为基准四舍无入到最接近的值，例如 0 小时、1.5 小时、3 小时、7.5 小时、478.5 小时等）

### 示例 3

以下代码...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...将产生与上述第一个示例类似的结果；但是，eVar1 的值会以秒、分钟、小时或天为单位返回，具体取决于计时器最终记录的时长。此外，计时器将在距首次设置之时 1 天后过期，而不是在访客关闭其浏览器时过期。

## 版本历史记录

### 2.1（2018 年 5 月 26 日）

* 包含对 `formatTime` 插件新版本所做的更改。

### 2.0（2018 年 4 月 6 日）

* 对插件进行了彻底重写/再分析。
