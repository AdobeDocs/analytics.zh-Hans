---
title: getVisitDuration
description: 跟踪访客在网站上停留的时间。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe插件：getVisitDuration

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getVisitDuration` 件跟踪访客在该时间段之前在网站上停留的时间（以分钟为单位）。 如果您希望跟踪到该时间为止站点上的累积时间，或跟踪执行活动所花费的时间，Adobe建议使用此插件。 该插件不跟踪事件之间的时间长短；如果需要此功能，请 [`getTimeBetweenEvents`](gettimebetweenevents.md) 使用插件。

## 使用Adobe Experience Platform Launch扩展安装插件

Adobe提供了一个扩展，允许您使用最常用的插件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到选 [!UICONTROL Extensions] 项卡，然后单击按 [!UICONTROL Catalog] 钮
1. 安装和发布扩 [!UICONTROL Common Analytics Plugins] 展
1. 如果尚未创建，请使用以下配置创建标有“初始化插件”的规则：
   * 条件：无
   * 事件：核心——载入的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常见分析插件
   * 操作类型：初始化getVisitDuration
1. 保存更改并发布到规则。

## 使用Launch自定义代码编辑器安装插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到选项卡， [!UICONTROL Extensions] 然后单击Adobe Analytics扩 [!UICONTROL Configure] 展下的按钮。
1. 展开折 [!UICONTROL Configure tracking using custom code] 叠面板，以显示按 [!UICONTROL Open Editor] 钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存更改并将其发布到Analytics扩展。

## 使用AppMeasurement安装插件

在实例化（使用）Analytics跟踪对象后，复制并粘贴AppMeasurement文件中的任意位置的以下代 [`s_gi`](../functions/s-gi.md)码。 在您的实施中保留代码的注释和版本号可帮助Adobe解决任何潜在问题。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getVisitDuration` 法不使用任何参数。 它返回以下值之一：

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (其 `[x]` 中是访客登录网站后经过的分钟数)

此插件创建一个名为的第一方Cookie `"s_dur"`，即访客登录网站后经过的毫秒数。 Cookie在30分钟不活动后过期。

## 示例调用

### 示例#1

以下代码……

```js
s.eVar10 = s.getVisitDuration();
```

...将始终设置eVar10等于访客登录网站后经过的分钟数

### 示例#2

以下代码……

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...使用inList插件检查events变量是否包含购买事件。  如果是，则eVar10将设置为等于访客开始访问与购买时间之间的分钟数。

### 示例#3

以下代码……

```js
s.prop10 = s.getVisitDuration();
```

...将始终设置prop10等于访客登录网站后所经过的分钟数。  如果prop10启用了路径分析，则此功能将很有用。  将“退出”量度添加到prop10报表中将显示一个细粒度的“散点图”报表，其中显示了访客离开网站前几分钟内的访问时间。

## 版本历史

### 2.0（2018年5月2日）

* 点发行（插件的完全重新分析／重写）。
