---
title: getTimeSinceLastVisit
description: 测量两次访问之间的间隔时间。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 100%

---


# Adobe 插件：getTimeSinceLastVisit

>[!IMPORTANT]
>
> 此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getTimeSinceLastVisit` 插件允许您跟踪访客在距上次访问后多久再次访问您的网站。

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
   * 操作类型：初始化 getTimeSinceLastVisit
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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getTimeSinceLastVisit` 方法不使用任何参数。此方法将返回距访客上次访问网站的间隔时间，并按以下列格式存储该时间：

* 若距上次访问的间隔时间介于 30 分钟和 1 小时之间，则会以“0.5 分钟”为基准将间隔时间四舍五入到最接近的值。例如 `"30.5 minutes"`、`"53 minutes"`
* 若距上次访问的间隔时间介于 1 小时和 1 天之间，则会以“0.25 小时”为基准将间隔时间四舍五入到最接近的值。例如 `"2.25 hours"`、`"7.5 hours"`
* 若距上次访问的间隔时间大于 1 天，则会以“1 天”为基准将间隔时间四舍五入到最接近的值。例如 `"1 day"`、`"3 days"`、`"9 days"`、`"372 days"`
* 如果访客之前未访问过，或间隔时间超过两年，则会将该值设为 `"New Visitor"`。

>[!NOTE]
>
> 此插件仅在访客在访问期间进行第一次点击时返回值。

此插件会创建一个名为 `"s_tslv"` 的第一方 Cookie，并将其设置为当前时间的 Unix 时间戳。Cookie 将在处于非活动状态两年后过期。

## 示例调用

### 示例 1

如果一位全新访客访问网站，且在访问的第一个页面上运行以下代码...

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

...会将 s.prop1 的值设置为等于“新访客”。

如果在处于非活动状态 35 分钟后在同一域上运行相同的代码，则会将 s.prop1 的值将设置为等于“35 分钟”。

如果在处于非活动状态 4 天后在同一域上运行相同的代码，则会将 s.prop1 的值将设置为等于“4 天”。

## 版本历史记录

### 1.0（2018 年 4 月 16 日）

* 修正版本（重新编译了代码，代码更小）。
* 从 `getDaysSinceLastVisit` 插件派生的代码（现已被弃用并重命名）。
* 现在对返回值使用 `formatTime` 和 `inList` 插件。
