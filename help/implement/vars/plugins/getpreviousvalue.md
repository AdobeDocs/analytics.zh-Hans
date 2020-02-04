---
title: getPreviousValue
description: 获取传递到变量的最后一个值。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe插件：getPreviousValue

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该 `getPreviousValue` 插件允许您将变量设置为上一次点击时的值。 如果您的实施包含当前点击中的所有所需值，则不需要此插件。

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
   * 操作类型：初始化getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getPreviousValue` 法使用以下参数：

* **`v`**（字符串，必需）:具有要传递给下一个图像请求的值的变量。 用于检索上一页`s.pageName`值的公用变量。
* **`c`**（字符串，可选）:存储值的Cookie的名称。  如果未设置此参数，则默认为`"s_gpv"`。

当您调用此方法时，它将返回包含在cookie中的字符串值。 然后，该插件会重置Cookie过期时间，并从参数中为其分配变量 `v` 值。 Cookie在30分钟不活动后过期。

## 示例调用

### 示例#1

以下代码……

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* 首先将s.prop7设置为与上一个图像请求中传递到s.pageName的值（即存储在“gpv_Page”cookie中的值）相等
* 然后，代码将重置“gpv_Page”cookie，使其等于s.pageName的当前值
* 如果运行此代码时未设置s.pageName，则代码将重置cookie的当前值的过期时间

### 示例#2

以下代码将s.prop7设置为与传递到s.pageName的最后一个值相等，但仅当在调用发生时，事件1也包含在s.events中时（通过inList插件确定）。

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 示例#3

以下代码将s.prop7设置为与传递到s.pageName的最后一个值相等，但前提是当前在页面上同时设置了s.pageName。

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 示例#4

以下代码将s.eVar10设置为与上一个图像请求中传递到s.eVar1的值相等。   以前的eVar1值应包含在“s_gpv”cookie中。  然后，代码将“s_gpv”cookie设置为与s.eVar1的当前值相等。

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## 不太可能的怪癖

如果与v参数关联的变量设置为新值并且getPreviousValue插件运行，但Analytics服务器调用未同时发送，则新v参数值在下次插件运行时仍被视为“上一个值”。
例如，假定以下代码在访问的第一页运行：

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

此代码将生成一个服务器调用，其中pageName参数等于“home”且未设置p7(prop7)参数。  但是，对s.getPreviousValue的调用将存储s.pageName(即“主页”)中指定的cookie（即“gpv_Page”cookie）。
现在，假定随后在同一页面上运行以下代码（无论原因如何）:

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

由于s.t()函数未在此代码块中运行，因此将不创建另一个图像请求。  但是，当s.getPreviousValue()函数代码此次运行时，s.prop7将设置为与s.pageName的先前值(即“home”)，然后将存储s.pageName的新值(即“gpv_Page”cookie中的“happy value”)。
假设访客导航到其他页面，并且此页面上运行以下代码：

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

运行s.t()调用函数时，它将创建一个图像请求，其中s.pageName=&quot;page 2&quot;和s.prop7等于“happy value”，该值是上次调用getPreviousValue时s.pageName的值。   “home”的s.prop7值从未包含在任何实际图像请求中，即使“home”是传递到s.pageName的第一个值。

## 版本历史

### v2.0（2019年10月7日）

* 点发行（完整逻辑重写）。
