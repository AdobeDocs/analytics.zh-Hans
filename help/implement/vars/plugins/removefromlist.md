---
title: rfl
description: 从以字符分隔的字符串中删除特定值。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：rfl（从列表中删除）

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `rfl` 件允许您“安全”地从分隔字符串(如、、列表变量 `events``products`和其他)中删除值。 如果您希望从分隔字符串中删除特定值而不担心分隔符，此插件非常有用。 其他几个插件依赖于此代码才能正确运行。 如果您不需要同时对多个Analytics变量运行特定函数，或者您未使用任何相关插件，则不需要此插件。

该插件使用以下逻辑：

* 如果要删除的值存在，则插件会保留变量中除要删除的值之外的所有内容。
* 如果要删除的值不存在，则插件会按原样保留原始字符串。

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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `rfl` 法使用以下参数：

* **`lv`**（必需，字符串）:包含分隔值列表的变量（或字符串）
* **`vr`**（必需，字符串）:您希望从参数中删除的`lv`值。 Adobe建议不要在一次调用期间删除多个`rfl`值。
* **`d1`**（可选，字符串）:参数使用的`lv`分隔符。 默认为逗号(`,`)。
* **`d2`**（可选，字符串）:您希望返回字符串使用的分隔符。 默认为与参数相同的`d1`值。
* **`df`**（可选，布尔）:如`true`果，则仅强制从参数中重复`vr`该参数的实`lv`例，而不是所有实例。 未设置`false`时，默认值为。

调用此方法将返回一个修改后的字符串，该字符串包含该 `lv` 参数，但不包含该参数中指定值的任何实例（或重复实例） `vr` 。

## 示例调用

### 示例#1

如果...

```js
s.events = "event22,event24,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event24");
```

...s.events的最终值将是：

```js
s.events = "event22,event25";
```

### 示例#2

如果...

```js
s.events = "event22,event24,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event26");
```

...s.events的最终值将是：

```js
s.events = "event22,event24,event25";
```

在此示例中，rfl调用对s.events未做任何更改，因为s.events不包含“event26”

### 示例#3

如果...

```js
s.events = "event22,event24,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events);
```

...s.events的最终值将是：

```js
s.events = "";
```

如果s.rfl调用中lv参数或vr参数为空，则插件将不返回任何内容

### 示例#4

如果...

```js
s.prop4 = "hello|people|today";
```

...下面的代码运行……

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

...s.prop4的最终值仍将是……

```js
s.prop4 = "hello|people|today";
```

...但s.eVar5的最终值将是：

```js
s.eVar5 = "hello|today";
```

请记住，该插件只返回一个值；实际上，它不会“重置”通过lv参数传入的变量。

### 示例#5

如果...

```js
s.prop4 = "hello|people|today";
```

...下面的代码运行……

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...s.prop4的最终值仍将是……

```js
s.prop4 = "hello|people|today";
```

如果lv参数值包含与默认值不同的分隔符（即逗号），请务必设置d1参数。

### 示例#6

如果...

```js
s.events = "event22,event23,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"EVenT23");
```

...s.events的最终值将是：

```js
s.events = "event22,event23,event25";
```

尽管此示例不实用，但它说明了在区分大小写的值中传递的必要性。

### 示例#7

如果...

```js
s.events = "event22,event23:12345,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event23");
```

...s.events的最终值将是：

```js
s.events = "event22,event25";
```

### 示例#8

如果...

```js
s.events = "event22,event23:12345,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event23:12345");
```

...s.events的最终值将是：

```js
s.events = "event22,event23:12345,event25";
```

当需要删除使用序列化和／或数字／货币语法的事件时，您应在s.rfl调用中仅指定事件本身（即不指定序列化／数字／货币值）。

### 示例#9

如果...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event23");
```

...s.events的最终值将是：

```js
s.events = "event22,event24,event25");
```

### 示例#10

如果...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

...s.events的最终值将是：

```js
s.events = "event22,event23,event24,event25");
```

### 示例#11

如果...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

...s.events的最终值将是：

```js
s.events = "event22|event23|event24|event25");
```

### 示例#12

如果...

```js
s.events = "event22,event23,event24,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event23,event24");
```

...s.events的最终值将是：

```js
s.events = "event22,event23,event24,event25";
```

不支持在vr参数中设置多个值。 上例中的rfl逻辑首先拆分lv参数（即s.events）中的值，然后尝试将每个分隔的值与完整的vr参数值(即“event23,event24”)。

### 示例#13

如果...

```js
s.events = "event22,event23,event24,event25";
```

...下面的代码运行……

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...s.events的最终值将是：

```js
s.events = "event22,event25");
```

从列表中删除的每个值都应包含在其自己的s.rfl调用中。

### 示例#14

如果...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...下面的代码运行……

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...s.linkTrackVars的最终值将为：

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

最后三个论点(即“,”、“,”、false)不是必需的，但是由于它们与默认设置匹配，因此不会因为位于此处而“伤害任何东西”。

### 示例#15

如果...

```js
s.events = "event22,event23,event24";
```

...下面的代码运行……

```js
s.rfl(s.events,"event23");
```

...s.events的最终值仍将是：

```js
s.events = "event22,event23,event24";
```

同样，请记住，插件只会返回一个值；实际上，它不会“重置”通过lv参数传入的变量。

## 版本历史

### 2.01（2019年9月17日）

* 默认分隔符值的次要错误修复

### 2.0（2018年4月16日）

* 点发行版（重新编译后，代码尺寸更小）。
* 删除了对插 `join` 件的需求。

### 1.0（2016年7月18日）

* 第一版。
