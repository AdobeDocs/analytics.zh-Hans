---
title: pt
description: 对变量列表执行一个函数。
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 100%

---

# Adobe 插件：pt

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`pt` 插件可对 Analytics 变量列表执行一个函数或方法。例如，您可以选择性地对多个变量运行 [`clearVars`](../functions/clearvars.md) 函数，而无需每次手动调用该函数。有一些其他插件需要此插件代码才能正常运行。如果您不需要同时对多个 Analytics 变量运行特定函数，或者您未使用任何依赖此插件的相关插件，则无需使用此插件。

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
    * Action Type: Initialize pt
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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`pt` 函数使用以下参数：

* **`l`**（必需，字符串）：可对其执行 `cf` 参数中包含的函数的变量列表。
* **`de`**（可选，字符串）：用于分隔 `l` 参数中变量列表的分隔符。默认使用逗号 (`,`)。
* **`cf`**（必需，字符串）：包含在 AppMeasurement 对象中且要针对 `l` 参数中所含每个变量而调用的回调函数的名称。
* **`fa`**（可选，字符串）：如果 `cf` 参数中的函数在运行时需要使用其他参数，请在此处包含这些参数。默认为 `undefined`。

如果回调函数（在 `cf` 参数中）返回一个值，则调用此函数也将返回一个值。

## 示例调用

### 示例 1

以下代码是 getQueryParam 插件的一部分。该代码会针对 URL querystring (fullQueryString) 中包含的每个键值对运行 getParameterValue 帮助程序函数。为了提取每个键值对，必须使用与号“&amp;”拆分 fullQueryString。parameterKey 是指插件尝试从查询字符串中提取的特定查询字符串参数

```js
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

以上代码行是运行如下所示代码的快捷方法：

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## 版本历史记录

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 2.01（2019 年 9 月 24 日）

* 对代码进行细微更改，以减小代码整体大小。

### 2.0（2018 年 4 月 17 日）

* 修正版本（重新编译，代码更小）。
* 增加了对 H 代码和 AppMeasurement 的支持。

### 1.0（2013 年 9 月 23 日）

* 第一版。
