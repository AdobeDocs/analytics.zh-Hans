---
title: apl(appendToList)
description: 将值追加到支持多个值的变量。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：apl(appendToList)

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `apl` 件允许您安全地向列表分隔的变量(如、、列表变量 `events``linkTrackVars`和其他变量)添加新值。

* 如果要添加的值在变量中不存在，则代码会将该值添加到字符串的结尾。
* 如果要添加的值在变量中已存在，则此插件不会更改该值。 此功能可让您的实施避免重复的值。
* 如果要添加到的变量为空，则插件会将该变量设置为新值。

如果要向包含分隔值字符串的现有变量添加新值，Adobe建议使用此插件。 如果您希望为包含分隔值的变量连接字符串，则不需要此插件。

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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `apl` 法使用以下参数：

* **`lv`**（必需，字符串）:包含要向
* **`vta`**（必需，字符串）:要添加到参数值的新值的以逗号分隔的`lv`列表。
* **`d1`**（可选，字符串）:用于分隔参数中已包含的各个值的分`lv`隔符。  未设置时，默`,`认为逗号()。
* **`d2`**（可选，字符串）:输出分隔符。 默认值与未设置时`d1`的值相同。
* **`cc`**（可选，布尔）:指示是否使用区分大小写的检查的标志。 如果`true`是，则复制检查区分大小写。 如果`false`未设置，复制检查将不区分大小写。 默认为`false`。

该方 `apl` 法返回参数的值加上 `lv` 参数中任何不重复的值 `vta` 。

## 示例调用

### 示例#1

如果...

```js
s.events = "event22,event24";
```

...下面的代码运行……

```js
s.events = s.apl(s.events, "event23");
```

...s.events的最终值将是：

```js
s.events = "event22,event24,event23";
```

### 示例#2

如果...

```js
s.events = "event22,event23";
```

...下面的代码运行……

```js
s.events = s.apl(s.events, "event23");
```

...s.events的最终值仍将是：

```js
s.events = "event22,event23";
```

在此示例中，APL调用未对s.events进行任何更改，因为s.events已包含“event23”

### 示例#3

如果...

```js
s.events = ""; //blank value
```

...下面的代码运行……

```js
s.events = s.apl(s.events, "event23");
```

...s.events的最终值将是……

```js
s.events = "event23";
```

### 示例#4

如果...

```js
s.prop4 = "hello|people";
```

...下面的代码运行……

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

...s.prop4的最终值仍将是……

```js
s.prop4 = "hello|people";
```

...但s.eVar5的最终值将

```js
s.eVar5 = "hello|people|today";
```

请记住，该插件只返回一个值；它不一定“重置”通过lv参数传入的变量。

### 示例#5

如果...

```js
s.prop4 = "hello|people";
```

...下面的代码运行……

```js
s.prop4 = s.apl(s.prop4, "today");
```

...s.prop4的最终值将为……

```js
s.prop4 = "hello|people,today";
```

请务必使分隔符在lv参数值中的内容与d1/d2参数中的内容之间保持一致

### 示例#6

如果...

```js
s.events = "event22,event23";
```

...下面的代码运行……

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

...s.events的最终值将是：

```js
s.events = "event22,event23,EVentT23";
```

尽管此示例不实用，但它表明在使用区分大小写的标志时需要小心。

### 示例#7

如果...

```js
s.events = "event22,event23";
```

...下面的代码运行……

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

...s.events的最终值将是：

```js
s.events = "event22,event23,event24,event25");
```

该插件不会将“event23”添加到s.events中，因为它已存在于s.events中。  但是，它会将event24和event25添加到s.events中，因为之前s.events中都不包含这两个事件。

### 示例#8

如果...

```js
s.linkTrackVars = "events,eVar1";
```

...下面的代码运行……

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

...s.linkTrackVars的最终值将为：

```js
s.linkTrackVars = "events,eVar1,campaign";
```

最后三个论点(即“,”、“,”、false)不是此apl调用结尾处的必要选项，但是由于它们与默认参数值匹配，因此设置这些选项也不会“伤害任何东西”。

### 示例#9

如果...

```js
s.events = "event22,event24";
```

...下面的代码运行……

```js
s.apl(s.events, "event23");
```

...s.events的最终值仍将是：

```js
s.events = "event22,event24";
```

单独运行插件（不将返回值指定给变量）实际上不会“重置”通过lv参数传入的变量。

### 示例#10

如果...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...下面的代码运行……

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

...s.list2的最终值将是：

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

由于两个分隔符参数不同，传入的值将由第一个分隔符参数(&quot;|&quot;)分隔，然后由第二个分隔符参数(&quot;-&quot;)连接在一起

## 版本历史

### 3.2（2019年9月25日）

* 修复了使用旧 `apl` 版本插件的调用的兼容性问题
* 删除了控制台警告以减小大小
* 添加了 `inList 2.1`

### 3.1（2018年4月22日）

* `d2` 参数现在默认为未设置 `d1` 时参数的值

### 3.0（2018年4月16日）

* 插件的完全重新分析／重写
* 添加了高级错误检查
* 该 `vta` 参数现在一次接受多个值
* 添加了 `d2` 参数以设置返回值的格式
* 将参数 `cc` 更改为布尔值

### 2.5（2016年2月18日）

* 现在使用比 `inList` 较处理的方法

### 2.0（2016年1月26日）

* `d` （分隔符）参数现在为可选参数（默认为逗号）
* `u` （区分大小写标记）参数现在为可选参数（默认为不区分大小写）
* 无论 `u` （区分大小写标记）参数如何，如果该值已存在于列表中，则插件不再向列表附加值