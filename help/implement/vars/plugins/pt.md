---
title: pt
description: 在变量列表上执行函数。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe插件：pt

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该 `pt` 插件可执行Analytics变量列表中的函数或方法。 例如，您可以选择性地对多个变 `clearVars` 量运行该方法，而无需每次手动调用该方法。 其他几个插件依赖于此代码才能正确运行。 如果您不需要同时对多个Analytics变量运行特定函数，或者您未使用任何相关插件，则不需要此插件。

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
   * 操作类型：初始化点
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `pt` 法使用以下参数：

* **`l`**（必需，字符串）:参数中包含的函数可针对的变`cf`量列表。
* **`de`**（可选，字符串）:分隔参数中变量列表的分`l`隔符。 默认为逗号(`,`)。
* **`cf`**（必需，字符串）:要针对参数中包含的每个变量调用的AppMeasurement对象中包含的回调函数的名`l`称。
* **`fa`**（可选，字符串）:如果参数中的函数在运`cf`行时调用其他参数，请在此处包含这些参数。 默认为`undefined`。

如果回调函数（在参数中）返回值，调用此方 `cf` 法将返回值。

## 示例调用

### 示例#1

以下代码是getQueryParam插件的一部分。  它针对URL的querystring(fullQueryString)中包含的每个键值对运行getParameterValue帮助函数。  另一种方法是，要提取每个键值对，fullQueryString必须用“&amp;”字符分隔并拆分。 parameterKey引用插件专门尝试从查询字符串中提取的查询字符串参数

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

以上代码行是运行代码的快捷方式，如下所示：

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = s.getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## 版本历史

### 2.01（2019年9月24日）

* 通过少量代码更改来减小总体大小

### 2.0（2018年4月17日）

* 点发行版（重新编译后，代码尺寸更小）。
* 增加了对H代码和AppMeasurement的支持。

### 1.0（2013年9月23日）

* 第一版。
