---
title: getTimeToComplete
description: 测量完成任务所花费的时间。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe插件：getTimeToComplete

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getTimeToComplete` 件跟踪用户在网站上完成进程所花费的时间。 “时钟”在调用操作时开 `start` 始，在调用操作时 `stop` 结束。 如果网站上有一个工作流程需要一些时间才能完成，并且您希望了解访客完成该工作需要多长时间，Adobe建议使用此插件。 如果您站点上的工作流需要很短的时间（少于3秒），则不必使用此插件，因为粒度只下降到完整秒。

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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getTimeToComplete` 法使用以下参数：

* **`sos`**（可选，字符串）:设置为`"start"`要启动计时器的时间。 设置为`"stop"`要停止计时器的时间。 默认为`"start"`。
* **`cn`**（可选，字符串）:用于存储开始时间的Cookie的名称。 默认为`"s_gttc"`。
* **`exp`**（可选，整数）:cookie（和计时器）过期的天数。 默认为`0`，表示浏览器会话的结束。

调用此方法将返回一个字符串，其中包含在操作和操作之间所花费的天数、小时数、分钟数和／或 `"start"` 秒 `"stop"` 数。

## 示例调用

### 示例#1

使用这些调用确定访客开始结帐过程和进行购买之间的时间。

访客开始结帐时启动计时器：

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

当访客进行购买时停止计时器，并将prop1设置为停止与开始之间的时差：

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1将捕获完成购买过程所需的时间

### 示例#2

如果要同时运行多个定时器（以测量不同的进程），您需要手动设置cn cookie参数。  例如，如果要测量完成购买所需的时间，您应设置以下代码……

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...但是，如果您还想测量（同时）填写注册表单所需的时间，您还应运行以下代码：

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

在第二个示例中，event1用于捕获注册过程的开始，该过程可能会因某种原因而需要7天才能完成，event2用于捕获注册的完成。  s.prop2将捕获完成注册过程所需的时间

## 版本历史

### 3.1（2019年9月30日）

* 添加了在第一个参数中需要值“start”或“stop”的逻辑。  传入的所有其他值都会阻止插件运行。
* 将 `inList 2.0` 插件更新为 `inList 2.1`。

### 3.0（2018年8月23日）

* 已将 `formatTime v1.0` 插件更新为 `formatTime v1.1`。

### 3.0（2018年4月17日）

* 点发行版（重新编译后，代码尺寸更小）。
* 若干小错误修复。

### 2.0 2016年6月21日)

* 消除了对插件 `p_fo` 的依赖性。
* 增加了与H-code和AppMeasurement的兼容性。
* 添加了控制台日志记录。
