---
title: inList
description: 检查另一个以字符分隔的值中是否包含值。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：inList

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `inList` 件允许您检查分隔字符串或JavaScript数组对象中是否已存在一个值。 其他几个插件的工 `inList` 作方式取决于插件。 与JavaScript方法相比，该插件具有一个明显的优 `indexOf()` 势，即它不匹配部分字符串。 例如，如果您使用此插件检查 `"event2"`，它与包含的字符串不匹配 `"event25"`。 如果您不需要检查分隔字符串或数组中的值，或者如果您要使用您自己的逻辑，则不需要此插 `indexOf()` 件。

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
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `inList` 法使用以下参数：

* **`lv`**（必需，字符串或数组）:要搜索的值或JavaScript数组对象的分隔列表
* **`vtc`**（必需，字符串）:要搜索的值
* **`d`**（可选，字符串）:用于分隔参数中各个值的分隔`lv`符。 未设置时，默`,`认为逗号()。
* **`cc`**（可选，布尔）:如果设置为`true`，则会进行区分大小写的检查。 如果设置为`false`或忽略，则进行不区分大小写的检查。 默认为`false`。

如果找到匹 `true` 配项，并且找不到匹配项， `false` 则调用此方法将返回。

## 示例调用

### 示例#1

如果...

```js
s.events="event22,event24";
```

...下面的代码运行……

```js
if(s.inList(s.events,"event22"))
```

...条件if语句为true

### 示例#2

如果...

```js
s.events="event22,event24";
```

...下面的代码运行……

```js
if(s.inList(s.events,"event2"))
```

...条件if语句将为false，因为inList调用未在event2和s.events中的分隔值之一之间做出精确匹配

### 示例#3

如果...

```js
s.events="event22,event24";
```

...下面的代码运行……

```js
if(!s.inList(s.events,"event23"))
```

...条件if语句将为true，因为inList调用未在event23和s.events中的分隔值之一之间做出精确匹配（请注意inList变量调用开头的“NOT”运算符）。

### 示例#4

如果...

```js
s.events = "event22,event23";
```

...下面的代码运行……

```js
if(s.inList(s.events,"EVenT23","",1))
```

...条件if语句为false。  尽管此示例不实用，但它表明在使用区分大小写的标志时需要小心。

### 示例#5

如果...

```js
s.linkTrackVars = "events,eVar1";
```

...下面的代码运行……

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...条件if语句为false。  传入调用的d参数的值(即&quot;|&quot;)假定s.linkTrackVars中的各个值以管道字符分隔，而实际上，这些值以逗号分隔。  在这种情况下，该插件将尝试在s.linkTrackVars(即“events,eVar1”)和要查找的值(即“eVar1”)。

## 版本历史

### v2.1（2019年9月26日）

* 为参数添加 `cc` 了不是布尔值的选项。 例如， `1` 是有效的案例检查值。

### v2.0（2018年4月17日）

* 点发行版（重新编译后，代码尺寸更小）。

### v1.01（2017年9月27日）

* 优化了代码以减小大小

### v1.0(2009)

* 第一版。


