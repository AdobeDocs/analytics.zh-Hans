---
title: apl (appendToList)
description: 将值附加到支持多个值的变量。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '1029'
ht-degree: 100%

---


# Adobe 插件：apl (appendToList)

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`apl` 插件允许您安全地向已列表分隔的变量（如 [`events`](../page-vars/events/events-overview.md)、[`linkTrackVars`](../config-vars/linktrackvars.md)、[`list`](../page-vars/list.md) 和其他变量）添加新值。

* 如果要添加的值在变量中不存在，则代码会将该值添加到字符串的结尾。
* 如果要添加的值在变量中已存在，则此插件不会更改该值。此功能可让您的实施避免出现重复的值。
* 如果要添加到的变量为空，则插件会将该变量设置为新值。

如果要向现有变量添加新值，并且现有变量包含由分隔值构成的字符串，Adobe 建议使用此插件。如果您要为包含分隔值的变量连接字符串，则不需要使用此插件。

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
   * 操作类型：初始化 APL（附加到列表）
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`apl` 方法使用以下参数：

* **`lv`**（必需，字符串）：包含要向其添加新值的已分隔列表的变量
* **`vta`**（必需，字符串）：要添加到 `lv` 参数值的以逗号分隔的新值列表。
* **`d1`**（可选，字符串）：用于分隔已包含在 `lv` 参数中的各个值的分隔符。如果未设置，则将默认使用逗号 (`,`)。
* **`d2`**（可选，字符串）：输出分隔符。如果未设置，则默认值与 `d1` 的值相同。
* **`cc`**（可选，布尔值）：指示是否使用区分大小写检查的标志。如果为 `true`，则重复检查区分大小写。如果为 `false` 或未设置，则重复检查不区分大小写。默认为 `false`。

`apl` 方法会返回 `lv` 参数的值以及 `vta` 参数中任何非重复值。

## 示例调用

### 示例 1

如果...

```js
s.events = "event22,event24";
```

...并运行以下代码...

```js
s.events = s.apl(s.events, "event23");
```

...s.events 的最终值将为：

```js
s.events = "event22,event24,event23";
```

### 示例 2

如果...

```js
s.events = "event22,event23";
```

...并运行以下代码...

```js
s.events = s.apl(s.events, "event23");
```

...s.events 的最终值仍将为：

```js
s.events = "event22,event23";
```

在此示例中，apl 调用未对 s.events 进行任何更改，因为 s.events 已包含“event23”

### 示例 3

如果...

```js
s.events = ""; //blank value
```

...并运行以下代码...

```js
s.events = s.apl(s.events, "event23");
```

...s.events 的最终值将为...

```js
s.events = "event23";
```

### 示例 4

如果...

```js
s.prop4 = "hello|people";
```

...并运行以下代码...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

...s.prop4 的最终值仍将为...

```js
s.prop4 = "hello|people";
```

...但 s.eVar5 的最终值将为

```js
s.eVar5 = "hello|people|today";
```

请记住，该插件只返回一个值；它不一定会“重置”通过 lv 参数传入的变量。

### 示例 5

如果...

```js
s.prop4 = "hello|people";
```

...并运行以下代码...

```js
s.prop4 = s.apl(s.prop4, "today");
```

...s.prop4 的最终值将为...

```js
s.prop4 = "hello|people,today";
```

请确保在 lv 参数值与 d1/d2 参数值之间保持分隔符一致

### 示例 6

如果...

```js
s.events = "event22,event23";
```

...并运行以下代码...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

...s.events 的最终值将为：

```js
s.events = "event22,event23,EVentT23";
```

尽管此示例不太符合实际，但它可以表明在使用区分大小写的标志时需要谨慎。

### 示例 7

如果...

```js
s.events = "event22,event23";
```

...并运行以下代码...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

...s.events 的最终值将为：

```js
s.events = "event22,event23,event24,event25");
```

该插件不会将“event23”添加到 s.events 中，因为它已存在于 s.events 中。但是，它会将 event24 和 event25 添加到 s.events 中，因为这两者之前均未包含在 s.events 中。

### 示例 8

如果...

```js
s.linkTrackVars = "events,eVar1";
```

...并运行以下代码...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

...s.linkTrackVars 的最终值将为：

```js
s.linkTrackVars = "events,eVar1,campaign";
```

此 apl 调用末尾的最后三个参数（即 &quot;,&quot;,&quot;,&quot;, false）不是必需的，但是由于它们与默认参数值匹配，因此即使设置它们也不会“造成任何不利影响”。

### 示例 9

如果...

```js
s.events = "event22,event24";
```

...并运行以下代码...

```js
s.apl(s.events, "event23");
```

...s.events 的最终值仍将为：

```js
s.events = "event22,event24";
```

单独运行此插件（不将返回值指定给变量）实际上不会“重置”通过 lv 参数传入的变量。

### 示例 10

如果...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...并运行以下代码...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

...s.list2 的最终值将为：

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

由于两个分隔符参数不同，传入的值将由第一个分隔符参数（“|”）分隔，然后由第二个分隔符参数（“-”）连接在一起

## 版本历史记录

### 3.2（2019 年 9 月 25 日）

* 修复了使用旧版插件的 `apl` 调用存在的兼容性问题
* 删除了控制台警告以减小大小
* 添加了 `inList 2.1`

### 3.1（2018 年 4 月 22 日）

* 如果未设置，则 `d2` 参数现在默认为 `d1` 参数的值

### 3.0（2018 年 4 月 16 日）

* 对插件进行了彻底的再分析/重写
* 添加了高级错误检查
* `vta` 参数现在一次可接受多个值
* 添加了 `d2` 参数以设置返回值的格式
* 将 `cc` 参数更改为布尔值

### 2.5（2016 年 2 月 18 日）

* 现在使用 `inList` 方法进行比较处理

### 2.0（2016 年 1 月 26 日）

* `d`（分隔符）参数现在为可选参数（默认为逗号）
* `u`（区分大小写标记）参数现在为可选参数（默认为不区分大小写）
* 无论 `u`（区分大小写标记）参数为何值，如果该值已存在于列表中，则插件都不会再向列表附加值