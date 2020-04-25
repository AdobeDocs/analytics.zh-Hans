---
title: rfl
description: 从字符分隔的字符串中删除特定值。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 插件：rfl（从列表中删除）

>[!IMPORTANT] 此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

The `rfl` plug-in allows you to &quot;safely&quot; remove values from delimited strings, such as [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md), and others. 如果您希望从分隔字符串中删除特定值且无需顾虑使用的分隔符，则可以使用此插件。有一些其他插件需要此插件代码才能正常运行。如果您不需要同时对多个 Analytics 变量运行特定函数，或者您未使用任何依赖此插件的相关插件，则无需使用此插件。

此插件将使用以下逻辑：

* 如果要删除的值存在，则插件会保留变量中除要删除的值之外的所有其他内容。
* 如果要删除的值不存在，则插件会按原样保留原始字符串。

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
   * 操作类型：初始化 RFP（从列表中删除）
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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`rfl` 方法使用以下参数：

* **`lv`**（必需，字符串）：包含分隔值列表的变量（或字符串）
* **`vr`**（必需，字符串）：要从 `lv` 参数中删除的值。Adobe 建议不要在一次 `rfl` 调用期间删除多个值。
* **`d1`**（可选，字符串）：`lv` 参数使用的分隔符。默认使用逗号 (`,`)。
* **`d2`**（可选，字符串）：您希望返回字符串使用的分隔符。默认为与 `d1` 参数的相同值。
* **`df`**（可选，布尔）：如果为 `true`，则仅从 `lv` 参数中强制删除重复的 `vr` 参数实例，而不是所有实例。如果未设置，则默认为 `false`。

调用此方法将返回一个修改后的字符串，该字符串将包含 `lv` 参数，但不包含 `vr` 参数中指定的值的任何实例（或重复实例）。

## 示例调用

### 示例 1

如果...

```js
s.events = "event22,event24,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event24");
```

...s.events 的最终值将为：

```js
s.events = "event22,event25";
```

### 示例 2

如果...

```js
s.events = "event22,event24,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event26");
```

...s.events 的最终值将为：

```js
s.events = "event22,event24,event25";
```

在此示例中，rfl 调用未对 s.events 做出任何更改，因为 s.events 中不包含“event26”

### 示例 3

如果...

```js
s.events = "event22,event24,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events);
```

...s.events 的最终值将为：

```js
s.events = "";
```

如果在 s.rfl 调用中 lv 参数或 vr 参数为空，则插件将不返回任何内容

### 示例 4

如果...

```js
s.prop4 = "hello|people|today";
```

...并运行以下代码...

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

...s.prop4 的最终值仍将为...

```js
s.prop4 = "hello|people|today";
```

...但 s.eVar5 的最终值将为：

```js
s.eVar5 = "hello|today";
```

请记住，此插件仅返回一个值；实际上，此插件不会“重置”通过 lv 参数传入的变量。

### 示例 5

如果...

```js
s.prop4 = "hello|people|today";
```

...并运行以下代码...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...s.prop4 的最终值仍将为...

```js
s.prop4 = "hello|people|today";
```

如果 lv 参数值包含的分隔符不同于默认分隔符（即逗号），请务必设置 d1 参数。

### 示例 6

如果...

```js
s.events = "event22,event23,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"EVenT23");
```

...s.events 的最终值将为：

```js
s.events = "event22,event23,event25";
```

尽管此示例不太符合实际，但它表明需要传递区分大小写的值。

### 示例 7

如果...

```js
s.events = "event22,event23:12345,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event23");
```

...s.events 的最终值将为：

```js
s.events = "event22,event25";
```

### 示例 8

如果...

```js
s.events = "event22,event23:12345,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event23:12345");
```

...s.events 的最终值将为：

```js
s.events = "event22,event23:12345,event25";
```

当需要删除使用序列化和/或数字/货币语法的事件时，您应仅在 s.rfl 调用中指定事件本身（即不指定序列化/数字/货币值）。

### 示例 9

如果...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event23");
```

...s.events 的最终值将为：

```js
s.events = "event22,event24,event25");
```

### 示例 10

如果...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

...s.events 的最终值将为：

```js
s.events = "event22,event23,event24,event25");
```

### 示例 11

如果...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

...s.events 的最终值将为：

```js
s.events = "event22|event23|event24|event25");
```

### 示例 12

如果...

```js
s.events = "event22,event23,event24,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event23,event24");
```

...s.events 的最终值将为：

```js
s.events = "event22,event23,event24,event25";
```

不支持在 vr 参数中设置多个值。上例中的 rfl 逻辑将先拆分 lv 参数（即 s.events）中的各个值，然后再尝试将每个分隔的值与完整的 vr 参数值（即 &quot;event23,event24&quot;）进行匹配。

### 示例 13

如果...

```js
s.events = "event22,event23,event24,event25";
```

...并运行以下代码...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...s.events 的最终值将为：

```js
s.events = "event22,event25");
```

要从列表中删除的每个值都应包含在其自己的 s.rfl 调用中。

### 示例 14

如果...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...并运行以下代码...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...s.linkTrackVars 的最终值将为：

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

此 s.rfl 调用末尾的最后三个参数（即 &quot;,&quot;,&quot;,&quot;,false）不是必需的，但是由于它们与默认设置匹配，因此即使它们存在也不会“造成任何不利影响”。

### 示例 15

如果...

```js
s.events = "event22,event23,event24";
```

...并运行以下代码...

```js
s.rfl(s.events,"event23");
```

...s.events 的最终值仍将为：

```js
s.events = "event22,event23,event24";
```

同样地，请记住，此插件仅返回一个值；实际上，此插件不会“重置”通过 lv 参数传入的变量。

## 版本历史记录

### 2.01（2019 年 9 月 17 日）

* 修复了关于默认分隔符值的小错误

### 2.0（2018 年 4 月 16 日）

* 修正版本（重新编译，代码更小）。
* 删除了使用 `join` 插件的需要。

### 1.0（2016 年 7 月 18 日）

* 第一版。
