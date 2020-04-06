---
title: getResponsiveLayout
description: 确定当前正在查看网站的哪个布局。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 插件：getResponsiveLayout

>[!IMPORTANT] 此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getResponsiveLayout` 插件允许您跟踪访客当前正在查看基于响应式设计的网站的哪个版本。如果您的网站使用响应式设计且您希望跟踪访客查看的网站版本，则 Adobe 建议您使用此插件。如果您的网站未使用响应式设计，则无需使用此插件。

## 使用 Adobe Experience Platform Launch 扩展安装此插件

Adobe 提供了一个扩展，通过该扩展，您可以使用一些最常用的插件。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. 安装和发布扩 [!UICONTROL Common Analytics Plugins] 展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化 getResponsiveLayout
1. 保存并发布对上述规则所做的更改。

## 使用 Launch 自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. 展开折 [!UICONTROL Configure tracking using custom code] 叠面板，以显示按 [!UICONTROL Open Editor] 钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getResponsiveLayout` 方法使用以下参数：

* **`ppw`**（必需，整数）：在页面从手机竖屏布局切换到手机横屏布局之前，浏览器窗口可以具有的最大宽度（以像素为单位）
* **`plw`**（必需，整数）：在页面从手机横屏布局切换到基于平板电脑布局之前，浏览器窗口可以具有的最大宽度（以像素为单位）
* **`tw`**（必需，布尔）：在页面从平板电脑布局切换到基于桌面的布局之前，浏览器窗口可以具有的最大宽度（以像素为单位）

调用此方法将返回一个由两部分构成的字符串。根据浏览器的宽度和上述参数，第一个部分将使用以下值：

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"`（适用于不同时具有纵向和横向布局的网站）
* `"tablet layout"`
* `"desktop layout"`

返回字符串的第二个部分是浏览器的宽度和高度尺寸。例如：`"desktop layout:1243x700"`。

## 示例调用

### 示例 1

如果...

* 当浏览器宽度大于 500 像素时，网站将从手机竖屏模式切换到手机横屏模式
* 当浏览器宽度大于 700 像素时，网站将从手机横屏模式切换到平板电脑模式
* 当浏览器宽度大于 1000 像素时，网站将从平板电脑模式切换到桌面模式

...以下代码会将 eVar10 设置为等于访客当前体验到的响应式设计布局以及浏览器的宽度和高度尺寸

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### 示例 2

如果...

* 您的网站只有手机模式、平板电脑模式和桌面模式
* 当浏览器宽度大于 500 像素时，网站将从手机模式切换到平板电脑模式
* 当浏览器宽度大于 1,100 像素时，网站将从平板电脑模式切换到桌面模式

...以下代码会将 eVar10 设置为等于访客当前体验到的响应式设计布局以及浏览器的宽度和高度尺寸

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## 版本历史记录

### 1.0（2018 年 5 月 2 日）

* 第一版。
