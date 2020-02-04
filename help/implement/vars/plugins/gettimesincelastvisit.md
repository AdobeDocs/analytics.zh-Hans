---
title: getTimeSinceLastVisit
description: 测量两次访问之间经过的时间。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe插件：getTimeSinceLastVisit

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getTimeSinceLastVisit` 件允许您跟踪访客在上次访问后回访您的网站所花费的时间。

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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getTimeSinceLastVisit` 法不使用任何参数。 它返回自访客上次访问网站以来经过的时间，以下列格式存储：

* 自上次访问以来30分钟到一小时的时间设置为最近的半分钟基准。 For example, `"30.5 minutes"`, `"53 minutes"`
* 一小时到一天之间的时间四舍五入到最接近的四分之一小时基准。 For example, `"2.25 hours"`, `"7.5 hours"`
* 大于一天的时间将舍入到最接近的日基准。 For example, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`
* 如果访客之前未访问过，或已用时间大于两年，则将该值设置为 `"New Visitor"`。

> [!NOTE] 此插件仅在访问的第一次点击时返回值。

此插件创建一个名为设置为当前时间的Unix `"s_tslv"` 时间戳的第一方Cookie。 Cookie在两年不活动后过期。

## 示例调用

### 示例#1

如果一个全新访客访问了该站点，并且在访问的第一页上运行了以下代码……

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

...s.prop1的值将设置为等于“新访客”。

如果同一代码在非活动状态持续35分钟后在同一域上运行，则s.prop1的值将设置为等于“35分钟”。

如果同一代码在进一步不活动4天后运行在同一域上，则s.prop1的值将设置为等于“4天”。

## 版本历史

### 1.0（2018年4月16日）

* 点发行（重新编译的代码和较小的大小）。
* 从插件派生 `getDaysSinceLastVisit` 的代码（现在已弃用和重命名）。
* 现在 `formatTime` 使用 `inList` 和插件获取返回值。
