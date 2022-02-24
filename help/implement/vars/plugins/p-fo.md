---
title: p_fo（仅限第一页）
description: 确保某些例程在每页上仅触发一次。
feature: Variables
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '635'
ht-degree: 100%

---

# Adobe 插件：p_fo（仅限第一页）

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`p_fo` 插件是用于检查特定 JavaScript 对象是否存在的实用工具。如果特定对象不存在，则此插件将创建该对象并返回 `true`。如果页面上已存在特定 JavaScript 对象，则将返回 `false`。此插件可用于确保代码仅在页面上运行一次。有一些其他插件需要此插件代码才能正常运行。如果您不担心代码在某个页面上运行的次数，或者您未使用任何依赖此插件的相关插件，则无需使用此插件。

## 使用 Adobe Experience Platform 中的标记安装插件

Adobe 提供了一个扩展，通过该扩展，您可以使用一些常用插件。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]按钮
1. 安装并发布[!UICONTROL 常用 Analytics 插件]扩展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化 p_fo
1. 保存并发布对上述规则所做的更改。

## 使用自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的[!UICONTROL 配置]按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`p_fo` 函数使用以下参数：

* **on**（必需，字符串）：插件将创建的 JavaScript 对象的名称，前提是页面上不存在该对象。

如果对象尚不存在，则此函数将返回 `true` 并创建该对象。如果对象尚已存在，则此函数将返回 `false`。

## 示例调用

### 示例 1

以下代码将检查页面中是否存在“myobject”对象。如果“myobject”对象不存在，则代码将创建“myobject”对象并返回值“true”。因此，将运行条件语句（即 Console.log(&#39;hello&#39;);）中的代码。

另一方面，如果在 p_fo 调用发生时“myobject”对象已存在，则 p_fo 函数将返回值“false”，条件语句将因此被视为 false。在这种情况下，将不运行条件语句中的代码。

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**注意：**&#x200B;每当加载新页面对象/DOM（或重新加载当前页面）时，on 参数中指定的对象将不复存在，因此 p_fo 插件将在页面完成加载后首次运行时再次返回 true。

## 版本历史记录

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 2.0

* 修正版本（重新编译，代码更小）。
* 将返回值类型从整数更改为布尔值

### 1.0

* 第一版。
