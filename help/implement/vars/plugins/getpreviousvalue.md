---
title: getPreviousValue
description: 获取传递到变量的上一个值。
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '888'
ht-degree: 100%

---


# Adobe 插件：getPreviousValue

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getPreviousValue` 插件允许您将一个变量设置为在上一次点击时设置的值。如果您的实施包含当前点击的所有所需值，则无需使用此插件。

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
   * 操作类型：初始化 getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getPreviousValue` 方法使用以下参数：

* **`v`**（字符串，必需）：具有要传递给下一个图像请求的值的变量。用于检索上一页值的常用变量为 `s.pageName`。
* **`c`**（字符串，可选）：用于存储值的 Cookie 的名称。如果未设置此参数，则将默认使用 `"s_gpv"`。

调用此方法时，将返回 Cookie 中包含的字符串值。然后，此插件会重置 Cookie 过期时间，并为其分配 `v` 参数中的变量值。该 Cookie 将在处于非活动状态 30 分钟后过期。

## 示例调用

### 示例 1

以下代码...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* 首先将 s.prop7 设置为等于在上一个图像请求中传递到 s.pageName 的值（即存储在“gpv_Page”Cookie 中的值）
* 然后，代码将重置“gpv_Page”Cookie，使其等于 s.pageName 的当前值
* 如果运行此代码时未设置 s.pageName，则代码将重置 Cookie 当前值的过期时间

### 示例 2

以下代码会将 s.prop7 设置为等于传递到 s.pageName 的上一个值，但前提是在调用发生时，event1 也包含在 s.events 中（通过 inList 插件确定）。

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 示例 3

以下代码会将 s.prop7 设置为等于传递到 s.pageName 的上一个值，但前提是当前还在页面上同时设置了 s.pageName。

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 示例 4

以下代码会将 s.eVar10 设置等于在上一个图像请求中传递到 s.eVar1 的值。上一个 eVar1 值应包含在“s_gpv”Cookie 中。然后，代码会将“s_gpv”Cookie 设置为等于 s.eVar1 的当前值。

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## 罕见情况

如果将与 v 参数关联的变量设为新值且运行 getPreviousValue 插件，但未同时发送 Analytics 服务器调用，则在下次运行插件时，仍会将 v 参数的新值视为“上一个值”。
例如，假定以下代码在访问的第一个页面上运行：

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

该代码将生成一个服务器调用，其中 pageName 参数等于“home”且未设置 p7 (prop7) 参数。但是，对 s.getPreviousValue 的调用会将 s.pageName 的值（即“home”）存储到在调用中指定的 Cookie（即“gpv_Page”Cookie）中。
现在，假定将紧接着在同一页面上运行以下代码（无论出于原因如何）：

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

由于此代码块中未运行 s.t() 函数，因此将不会再创建图像请求。但是，如果此时运行 s.getPreviousValue() 函数代码，则会将 s.prop7 设置为等于 s.pageName 的上一个值（即“home”），然后将 s.pageName 的新值（即“happy value”）存储到“gpv_Page”Cookie 中。
假设访客导航到其他页面，并且以下代码在该页面上运行：

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

运行 s.t() 调用函数时，将创建一个图像请求，其中 s.pageName=&quot;page 2&quot; 和 s.prop7 等于“happy value”，该值是上次调用 getPreviousValue 时 s.pageName 的值。虽然 s.prop7 的值“home”是传递到 s.pageName 的第一个值，但“home”从未包含在任何实际图像请求中。

## 版本历史记录

### v2.0（2019 年 10 月 7 日）

* 修正版本（对逻辑进行了彻底重写）。
