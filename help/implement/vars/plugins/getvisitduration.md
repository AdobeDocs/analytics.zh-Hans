---
title: getVisitDuration
description: 跟踪访客在网站上停留的时间。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe插件：getVisitDuration

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getVisitDuration` 件跟踪访客在该时间段之前在网站上停留的时间（以分钟为单位）。 如果您希望跟踪到该时间为止站点上的累积时间，或跟踪执行活动所花费的时间，Adobe建议使用此插件。 该插件不跟踪事件之间的时间长短；如果需要此功能，请 `getTimeBetweenEvents` 使用插件。

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
