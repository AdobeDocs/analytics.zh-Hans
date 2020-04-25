---
title: getVisitDuration
description: 跟踪访客在网站上停留的时间。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 插件：getVisitDuration

>[!IMPORTANT] 此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getVisitDuration` 插件可跟踪访客在某个时间点之前在网站上停留的时间（以分钟为单位）。如果您希望跟踪截至某个时间点为止访客在网站上停留的总时间，或跟踪访客执行某项活动所用的时间，Adobe 建议您使用此插件。此插件不会跟踪事件之间的间隔时间；如果需要使用此功能，请使用 [`getTimeBetweenEvents`](gettimebetweenevents.md) 插件。

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
   * 操作类型：初始化 getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getVisitDuration` 方法不使用任何参数。它会返回以下任一值：

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"`（其中 `[x]` 是自访客登录网站后所经过的时间，以分钟为单位）

此插件将创建一个名为 `"s_dur"` 的第一方 Cookie，用于记录自访客登录网站起所经过的时间（以毫秒为单位）。该 Cookie 将在处于非活动状态 30 分钟后过期。

## 示例调用

### 示例 1

以下代码...

```js
s.eVar10 = s.getVisitDuration();
```

...会始终将 eVar10 设置为等于自访客登录网站后所经过的时间（以分钟为单位）

### 示例 2

以下代码...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...会使用 inList 插件检查 events 变量是否包含购买事件。如果包含，则会将 eVar10 设置为等于从访客开始访问到进行购买所间隔的时间（以分钟为单位）。

### 示例 3

以下代码...

```js
s.prop10 = s.getVisitDuration();
```

...会始终将 prop10 设置为自访客登录网站后所经过的时间（以分钟为单位）。如果 prop10 启用了路径分析，则此设置将很有用。将“退出次数”量度添加到 prop10 报表中将显示一个细粒度的“散点图”报表，其中将显示访客离开网站前访问所花费的时间（以分钟为单位）。

## 版本历史记录

### 2.0（2018 年 5 月 2 日）

* 修正版本（对插件进行了彻底再分析/重写）。
