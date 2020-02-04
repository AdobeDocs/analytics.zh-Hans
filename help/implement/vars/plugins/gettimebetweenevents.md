---
title: getTimeBetweenEvents
description: 测量两个事件之间的时间。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：getTimeBetweenEvents

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getTimeBetweenEvents` 件允许您跟踪任意两个Analytics事件（包括购物车和自定义事件）之间的时间长度。 它可用于跟踪结帐流程完成或您想要测量时间的任何其他流程所需的时间。 如果您没有任何要测量转换时间的转换过程，则无需使用此插件。

## 使用Adobe Experience Platform Launch扩展安装插件

Adobe提供了一个扩展，允许您使用最常用的插件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击“目 [!UICONTROL 录] ”按钮
1. 安装和发布 [!UICONTROL Common Analytics插件扩展]
1. 对于要使用插件的任何启动规则，请添加一个具有以下配置的操作：
   * 扩展：常见分析插件
   * 操作类型：初始化addProductEvar
1. 保存更改并发布到规则

## 使用Launch自定义代码编辑器安装插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics扩 [!UICONTROL 展下的] “配置”按钮。
1. 使用自定 [!UICONTROL 义代码accordion展开“配置跟踪] ”，该面板显示“打 [!UICONTROL 开编辑器] ”按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存更改并将其发布到Analytics扩展。

## 使用AppMeasurement安装插件

在实例化（使用）Analytics跟踪对象后，复制并粘贴AppMeasurement文件中的任意位置的以下代 `s_gi`码。 在您的实施中保留代码的注释和版本号可帮助Adobe解决任何潜在问题。

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

## 使用插件

该方 `getTimeBetweenEvents` 法使用以下参数：

* **`ste`**（必需，字符串）:启动计时器事件。 用于“启动计时器”的Analytics事件的逗号分隔字符串。
* **`rt`**（必需，布尔）:重新启动计时器选项。 如果要`true`在每次变量包含启动计时器事件时重新`events`启动计时器，则设置为。 如果不`false`希望计时器在看到开始计时器事件时重新启动，则设置为。
* **`stp`**（必需，字符串）:停止计时器事件。 逗号分隔的“停止计时器”Analytics事件字符串。
* **`res`**（必需，布尔）:重置计时器选项。 如果要`true`记录计时器启动后的时间，则设置为，并在计时器停止后重置计时器。 如果`false`要录制时间，但不停止计时器，则设置为。 如果设置为`false`，则在events变量记录停止事件后，计时器将继续运行。
   > [!TIP] 如果将此参数设置为， `false`则强烈建议在 `rte` 下面设置参数。
* **`cn`**（可选，字符串）:存储第一个事件的时间的Cookie名称。 默认为`"s_tbe"`。
* **`etd`**（可选，整数）:cookie的过期时间（以天为单位）。 设置为`0`在浏览器会话结束时过期。 未设置时，默认为1天。
* **`fmt`**（可选，字符串）:返回秒数的时间格式（默认为无）
   * `"s"` 秒
   * `"m"` 几分钟
   * `"h"` 数小时
   * `"d"` 天数
   * 如果未设置，则返回值的格式基于以下规则：
      * 小于一分钟的任意值将舍入到最接近的5秒基准值。 例如，10秒，15秒
      * 一分钟到一小时之间的任何内容，都四舍五入到最接近的1/2分钟基准。 例如，30.5分钟，31分钟
      * 一小时到一天之间的任何内容都舍入到最接近的四分之一小时基准。 例如，2.25小时，3.5小时
      * 任何大于一天的项目都会舍入到最接近的日基准。 例如，1天，3天，9天
* **`bml`**（可选，数字）:根据参数格式的舍入基准的长`fmt`度。 例如，如果参数`fmt`为，`"s"`且此参数为，则返回`2`值将舍入到最接近的2秒基准。 如果`fmt`参数为`"m"`且此参数为，则返回值`0.5`将舍入到最接近的半分钟基准值。
* **`rte`**（可选，字符串）:删除或删除计时器的Analytics事件的逗号分隔字符串。 默认为无。

调用此方法将返回一个整数，该整数表示以所需格式开始计时器事件和停止计时器事件之间的时间量。

## 示例调用

### 示例#1

以下代码……

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...配置为按如下方式行事：

* 计时器将在s.events包含event1时开始。
* 每次s.events包含event1时，计时器将重新启动
* 当s.events包含event2时，计时器将停止
* 每次s.events包含event2时，计时器将重置（即转到0秒）
* 当s.events包含event3或访客关闭其浏览器时，计时器也会重置
* 当记录event1和event2之间的实际时间时，插件将设置eVar1等于设置的两个事件之间的秒数，舍入到最接近的2秒基准（例如0秒、2秒、4秒、10秒、184秒等）
* 如果s.events在计时器启动之前包含event2，则根本不会设置eVar1。

### 示例#2

以下代码……

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...配置为按如下方式行事：

* 计时器将在s.events包含event1时开始。
* 计时器不会在s.events包含event1时每次重新启动，而原始计时器仍将继续运行
* 当s.events包含event2时，计时器将不停止，但插件将记录自记录原始event1设置以来的时间
* 计时器存储在名为“s_20”的Cookie中
* 仅当s.events包含event3时，或者自计时器启动以来已经过20天时，计时器才会重置
* 在记录（原始）event1和event2之间的时间时，插件会将eVar1设置为两个事件之间的小时数，并舍入到最接近的1个1/2小时基准（例如0小时、1.5小时、3小时、7.5小时、478.5小时等）

### 示例#3

以下代码……

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...将产生与上述第一个示例类似的结果；但是，eVar1的值会在秒、分钟、小时或天内返回，具体取决于计时器的最终长度。  此外，计时器将在首次设置后1天过期，而不是访客关闭其浏览器时。

## 版本历史

### 2.1（2018年5月26日）

* 适应对插件新版本所 `formatTime` 做的更改。

### 2.0（2018年4月6日）

* 插件的完全重写／重新分析。
