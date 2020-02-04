---
title: getResponsiveLayout
description: 确定当前正在查看网站的哪个布局。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe插件：getResponsiveLayout

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getResponsiveLayout` 件可让您跟踪访客当前正在查看的基于设计的响应式网站的哪个版本。 如果您的站点使用响应式设计并希望跟踪访客查看的站点版本，则Adobe建议使用此插件。 如果您的站点不使用响应式设计，则不需要此插件。

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
   * 操作类型：初始化getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getResponsiveLayout` 法使用以下参数：

* **`ppw`**（必需，整数）:在页面从电话纵向布局切换到电话横向布局之前，浏览器窗口可以具有的最大像素宽度
* **`plw`**（必需，整数）:在页面从电话横向布局切换到基于平板电脑的布局之前，浏览器窗口可具有的最大像素宽度
* **`tw`**（必需，布尔）:在页面从平板电脑布局切换到基于桌面的布局之前，浏览器窗口可以具有的最大像素宽度

调用此方法将返回包含两部分的字符串。 第一部分根据浏览器的宽度和上述参数使用以下值：

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` （对于不同时具有纵向和横向布局的站点）
* `"tablet layout"`
* `"desktop layout"`

返回字符串的第二部分是浏览器的宽度和高度尺寸。 例如：`"desktop layout:1243x700"`。

## 示例调用

### 示例#1

如果...

* 当浏览器宽度大于500像素时，站点将从电话纵向模式切换到电话横向模式
* 当浏览器宽度大于700像素时，站点将从手机横向模式切换到平板电脑模式
* 当浏览器宽度大于1000像素时，站点从平板电脑模式切换到桌面模式

...以下代码将eVar10设置为与访客当前的响应式设计布局相等的体验以及浏览器的宽度和尺寸

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### 示例#2

如果...

* 您的站点只有电话模式、平板电脑模式和桌面模式
* 当浏览器宽度大于500像素时，站点将从手机模式切换到平板电脑模式
* 当浏览器宽度大于1,100像素时，站点从平板电脑模式切换到桌面模式

...以下代码将eVar10设置为与访客当前的响应式设计布局相等的体验以及浏览器的宽度和尺寸

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## 版本历史

### 1.0（2018年5月2日）

* 第一版。
