---
title: formatTime
description: 将秒数转换为以分钟、小时等为单位的等效时间。
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Adobe插件：formatTime

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `formatTime` 件允许您花费任意秒数，并以分时段格式显示它们，舍入到所需的基准值。 如果您希望以秒为单位捕获时间值并将其转换为时段格式（如分钟、天或周）,Adobe建议使用此插件。 如果您不想将基于秒的值存储为时间舍入格式，则不需要此插件。

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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `formatTime` 法使用以下参数：

* **`ns`**（必需，整数）:转换或格式化的秒数
* **`tf`**（可选，字符串）:返回秒的格式类型；默认为秒
   * 如果您 `"d"` 希望时间（以天为单位），则设置为（默认情况下，舍入到最接近的1/4天基准）
   * 如果您 `"h"` 希望时间（以小时为单位），则设置为（默认情况下，舍入到最接近的1/4小时基准）
   * 如果您 `"m"` 希望时间（以分钟为单位），则设置为（默认情况下，舍入到最接近的1/2分钟基准）
   * 如果您 `"s"` 希望时间（以秒为单位），则设置为（默认情况下，舍入到最接近的5秒基准）
* **`bml`**（可选，数字）:舍入基准的长度。 默认为参数中列出的基准`tf`测试

该方法返回使用参数中指定的单位格式化的秒 `tf` 数。 如果未 `tf` 设置参数：

* 小于一分钟的任意值将舍入到最接近的5秒基准值
* 一分钟到一小时之间的任何内容，均四舍五入到最接近的1/2分钟基准
* 一小时到一天之间的任何内容均四舍五入为最接近的四分之一小时基准
* 任何大于一天的内容均四舍五入到最接近的日基准

## 示例

### 示例#1

以下代码……

```js
s.eVar1 = s.formatTime(38242);
```

...将s.eVar1设置为等于“10.5小时”

传入的参数（38242秒）等于10小时、37分钟和22秒。  由于此调用中未设置tf参数，且传入的秒数介于1小时和1天之间，因此插件将返回转换为最接近的四分之一小时基准的秒数。

### 示例#2

以下代码……

```js
s.eVar1 = s.formatTime(38250);
```

...will set s.eVar1 equal to &quot;10.75 hours&quot;传入的参数- 38250秒——等于10小时、37分钟和30秒。  在这种情况下，舍入传递给最接近的季度小时基准的秒数会将最终值设置为10.75小时

### 示例#3

以下代码……

```js
s.eVar1 = s.formatTime(38242, "m");
```

...将s.eVar1设置为等于“637.5分钟”

在这种情况下，“m”参数会强制插件将秒数转换为最接近的半分钟基准

### 示例#4

以下代码……

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...将s.eVar1设置为等于“640分钟”

tf参数值(“m”)强制插件将秒数转换为分钟数，但bml参数值(20)也强制插件将分钟数转换为最接近的20分钟基准数。

### 示例#5

以下代码……

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...将s.eVar1设置为“126秒”，这是最接近的2秒基准为125秒

### 示例#6

以下代码……

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...将s.eVar1设置为等于“3分钟”，这是最接近的3分钟基准为125秒

### 示例#7

以下代码……

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...将s.eVar1设置为“2.4分钟”，这是最接近的2/5ths分钟基准(例如，.4 = 2/5)至145秒

## 版本历史

### 1.1（2018年5月21日）

* 添加了该 `bml` 参数，以便在舍入方面更灵活

### 1.0（2018年4月15日）

* 初始版本。
