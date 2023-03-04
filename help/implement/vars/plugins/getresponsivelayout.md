---
title: getResponsiveLayout
description: 确定当前正在查看网站的哪个布局。
feature: Variables
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 100%

---

# Adobe 插件：getResponsiveLayout

{{plug-in}}

`getResponsiveLayout` 插件允许您跟踪访客当前正在查看基于响应式设计的网站的哪个版本。如果您的网站使用响应式设计且您希望跟踪访客查看的网站版本，则 Adobe 建议您使用此插件。如果您的网站未使用响应式设计，则无需使用此插件。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getResponsiveLayout
1. Save and publish the changes to the rule.-->

## 使用自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getResponsiveLayout` 函数使用以下参数：

* **`ppw`**（必需，整数）：在页面从手机竖屏布局切换到手机横屏布局之前，浏览器窗口可以具有的最大宽度（以像素为单位）
* **`plw`**（必需，整数）：在页面从手机横屏布局切换到基于平板电脑布局之前，浏览器窗口可以具有的最大宽度（以像素为单位）
* **`tw`**（必需，布尔）：在页面从平板电脑布局切换到基于桌面的布局之前，浏览器窗口可以具有的最大宽度（以像素为单位）

调用此函数将返回一个字符串，其中包含以冒号 (`:`) 分隔的两个部分。根据浏览器的宽度和上述参数，该字符串的第一个部分包含下列值之一：

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"`（适用于不同时具有纵向和横向布局的网站）
* `"tablet layout"`
* `"desktop layout"`

返回字符串的第二个部分是浏览器的宽度和高度尺寸。例如：`"desktop layout:1243x700"`。

## 示例

```js
// A visitor accesses your site on their laptop. The browser window is maximized.
// * Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
// * Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels
// Sets eVar10 to "desktop layout:1920x937".
s.eVar10 = getResponsiveLayout(500, 700, 1000);

// A visitor accesses your site on their phone.
// * Your site has only a phone mode, a tablet mode, and a desktop mode
// * Your site switches from phone mode to tablet mode when the browser width is greater than 800 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels
// Sets eVar10 to "phone portrait layout:720x1280"
s.eVar10 = getResponsiveLayout(800, 800, 1100);
```

## 版本历史记录

### 1.1（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 1.0（2018 年 5 月 2 日）

* 第一版。
