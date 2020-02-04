---
title: getAndPersistValue
description: 存储稍后可随时检索的值。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：getAndPersistValue

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getAndPersistValue` 件允许您在cookie中存储一个值，该值可在访问期间稍后检索。 它的作用与Adobe Experience Platform Launch中的“存 [!UICONTROL 储持续时间] ”功能类似。 如果您希望在设置变量后的后续点击中自动将Analytics变量保留为相同的值，Adobe建议使用此插件。 如果Launch的“存储持续时间  ”功能足够，或者您无需在后续点击中将变量设置为相同值并将其保留为相同值，则无需使用此插件。 eVar的内置持久性不需要使用此插件，因为这些变量在服务器端由Adobe保留。

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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getAndPersist` 法使用以下参数：

* **`vtp`**（必需）:要在页面之间保留的值
* **`cn`**（可选）:用于存储值的Cookie的名称。 如果未设置此参数，则命名Cookie`"s_gapv"`
* **`ex`**（可选）:cookie过期前的天数。 如果此参数`0`已设置或未设置，则Cookie将在访问结束时过期（30分钟不活动）。

如果参数中的 `vtp` 变量已设置，则插件会设置cookie，然后返回cookie值。 如果未设置 `vtp` 参数中的变量，则插件只返回cookie值。

## 示例

### 示例#1

以下代码将eVar21设置为与“hello”的值相等。  然后，该代码将设置ev21gapv cookie，该cookie将在28天后过期，等于eVar21的值(即“你好”)。  然后，代码将eVar21（重新）设置为ev21gapv cookie的值。

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例#2

假定eVar21尚未在当前页面上设置，但在过去28天内设置为与上一页面上的“hello”相等。   以下代码将仅将eVar21设置为与ev21gapv cookie的值相等(即“你好”)。  它不会重置ev21gapv cookie，因为调用函数之前未在当前页面上设置eVar21。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例#3

假定eVar21尚未在当前页面上设置，但在过去28天内设置为与上一页面上的“hello”相等。  以下代码将仅将prop35设置为等于ev21gapv cookie的值(即“你好”)。  它不会设置eVar21。

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例#4

以下代码将eVar21设置为等于“howdy”的值。  然后，该代码将设置（或重置）ev21gapv cookie，该cookie将在28天后过期，等于eVar21的值(即“你好”)。  然后，代码将prop35设置为ev21gapv cookie的值(即“你好”)。

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例#5

假定在过去28天内，未在任何页面上设置s.eVar21。  以下代码将s.eVar21设置为“无”，因为ev21gapv cookie将在上次设置后的28天后过期。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例#6

以下代码将eVar30设置为等于“shopping”。  然后，它将s_gapv cookie设置为等于s.eVar30(即，“购物”)。  然后，它将s.eVar30设置为s_gapv cookie的值（即getAndPersistValue调用返回s_gapv cookie的值，在本例中为“shopping”）。

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

如果s.eVar30未设置为会话期间看到的任何其他页面上的显式值，但通过以下代码设置（在doPlugins中）。..

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30将设置为与“shopping”相等（即s_gapv cookie的持续值）

## 版本历史

### 2.0（2018年4月16日）

* 点发行（较小的代码大小）
* 现在，将0传递 `ex` 到参数将强制在30分钟不活动后过期，而不是在浏览器会话结束时过期。

### 1.0（2016年1月18日）

* 第一版。
