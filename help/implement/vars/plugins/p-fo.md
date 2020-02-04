---
title: p_fo（仅限页面优先）
description: 确保某些例程每页只触发一次。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：p_fo（仅限页面优先）

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

插 `p_fo` 件是检查特定JavaScript对象是否存在的实用程序。 如果该对象不存在，则插件将创建该对象并返回 `true`。 如果页面上已存在JavaScript对象，则返回该对象 `false`。 此插件对于在页面上仅运行一次代码非常有用。 其他几个插件依赖此代码才能工作。 如果您不担心某个页面上的代码运行次数或未使用任何相关插件，则无需使用此插件。

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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `p_fo` 法使用以下参数：

* **on** (required, string):插件在页面上尚不存在时创建的JavaScript对象的名称。

如果该对象尚不存在，则此方法将返回并 `true` 创建该对象。 如果对象已存在，则此方法返回 `false`。

## 示例调用

### 示例#1

以下代码将检查页面中是否存在“myobject”对象。  如果“myobject”对象不存在，则代码将创建“myobject”对象并返回值true。  因此，条件语句(即Console.log(&#39;hello&#39;);)中的代码将运行。

另一方面，如果在p_fo调用发生时“myobject”对象已经存在，则p_fo函数将返回false的值，因此条件语句将被视为false。  在这种情况下，条件语句中的代码将不运行。

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**** 注意：每次加载新页面对象/DOM（或当前页面重新加载）时，on参数中指定的对象将不再存在，因此p_fo插件在页面完成加载后首次运行时将再次返回true。

## 版本历史

### 2.0

* 点发行版（重新编译后，代码尺寸更小）。
* 将返回值类型从整数更改为布尔值

### 1.0

* 第一版。
