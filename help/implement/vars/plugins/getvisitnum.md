---
title: getVisitNum
description: 跟踪访客的当前访问次数。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe插件：getVisitNum

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该 `getVisitNum` 插件会返回在所需天数内访问网站的所有访客的访问次数。 Analysis Workspace提供了一个“访问次数”维度，该维度提供类似的功能。 如果您希望对访问次数的递增方式有更多控制权，Adobe建议使用此插件。 如果Analysis Workspace中内置的“访问次数”维度足以满足您的报告需求，则不必使用此插件。

## 使用Adobe Experience Platform Launch扩展安装插件

Adobe提供了一个扩展，允许您使用最常用的插件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击“目 [!UICONTROL 录] ”按钮
1. 安装和发布 [!UICONTROL Common Analytics插件扩展]
1. 如果尚未创建，请使用以下配置创建标有“初始化插件”的规则：
   * 条件：无
   * 事件：核心——载入的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常见分析插件
   * 操作类型：初始化getVisitNum
1. 保存更改并发布到规则。

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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getVisitNum` 法使用以下参数：

* **`rp`**（可选，整数OR字符串）:访问次数计数器重置前的天数。  未设置`365`时，默认值为。
   * 当此参数 `"w"`为时，计数器将在周末重置（本周六晚上11:59）
   * 当此参数 `"m"`为时，计数器将在月末（本月的最后一天）重置
   * 当此参数 `"y"`为时，计数器将在年末（12月31日）重置
* **`erp`**（可选，布尔）:当参`rp`数是数字时，此参数确定访问号是否应延长。 如果设置为`true`，则您站点的后续点击将重置访问次数计数器。 如果设置为`false`，则访问次数计数器重置时，您站点的后续点击不会延长。 默认为`true`。 当参数为字符串时，`rp`此参数无效。

访客在非活动状态持续30分钟后返回您的网站时，访问次数会增加。 调用此方法将返回一个表示访客当前访问次数的整数。

此插件设置一个名为的第一方Cookie, `"s_vnc[LENGTH]"` 其 `[LENGTH]` 中是传递到参数中的 `rp` 值。 For example, `"s_vncw"`, `"s_vncm"`, or `"s_vnc365"`. cookie的值是表示访问计数器重置的时间（如周末、月末或非活动状态持续365天后）的Unix时间戳的组合。 它还包含当前访问号。 此插件设置另一个名为的Cookie, `"s_ivc"` 该Cookie设置为在30分钟 `true` 不活动后过期。

## 示例调用

### 示例#1

对于最近365天内未访问过网站的访客，以下代码将s.prop1设置为值1:

```js
s.prop1=s.getVisitNum();
```

### 示例#2

对于首次访问后364天内返回网站的访客，以下代码将s.prop1设置为等于2:

```js
s.prop1=s.getVisitNum(365);
```

如果此访客在第二次访问后364天内返回网站，则以下代码将s.prop1设置为等于3:

```js
s.prop1=s.getVisitNum(365);
```

### 示例#3

对于首次访问后179天内返回网站的访客，以下代码将s.prop1设置为等于2:

```js
s.prop1=s.getVisitNum(180,false);
```

但是，如果此访客在第二次访问后1天或多天返回网站，则以下代码将s.prop1设置为等于1:

```js
s.prop1=s.getVisitNum(180,false);
```

当调用中的第二个参数等于false时，确定访问号码何时应“重置”为1的例程将在访客首次访问网站后的“x”天数（在本例中，为365天）中执行此操作。

当第二个参数等于true（或根本未设置）时，插件将仅在“x”天数（此示例中为365天）访客不活动后才将访问次数重置为1。

### 示例#4

对于在当周（从星期日开始）首次访问网站的所有访客，以下代码将s.prop1设置为等于1:

```js
s.prop1=s.getVisitNum("w");
```

### 示例#5

对于当月（从每月的第一天开始）首次访问网站的所有访客，以下代码将s.prop1设置为等于1:

```js
s.prop1=s.getVisitNum("m");
```

请记住，getVisitNum插件不考虑基于零售的日历（即4-5-4、4-4-5等）

### 示例#6

对于本年度（从1月1日开始）首次访问网站的所有访客，以下代码将s.prop1设置为等于1:

```js
s.prop1=s.getVisitNum("y");
```

### 示例#7

如果您希望跟踪某周访客的访问次数、某月访客的访问次数和该年访客的访问次数（所有这些都在不同的Analytics变量中），则应使用类似于以下代码的代码：

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

在这种情况下，该插件将创建三个不同的cookies（每个不同时间段对应一个cookie），以跟踪每个时间段的单个访问次数。

## 版本历史

### 4.11（2019年9月30日）

* 修复了参数显 `erp` 式设置为的问题 `false`。

### 4.1（2018年5月21日）

* 已将 `endOfDatePeriod` 插件更新为v1.1。

### 4.0（2018年4月17日）

* 点发行版（重新编译后，代码尺寸更小）。
* 删除了Cookie参数作为插件，现在可基于该参数动态生成Cookie `rp` )

### 3.0（2016年6月5日）

* 全面检修
* 将插件不同版本中可用的所有先 `getVisitNum` 前解决方案组合在一起。
