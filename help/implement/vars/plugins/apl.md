---
title: apl (appendToList)
description: 将值附加到支持多个值的变量。
feature: Variables
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 90%

---

# Adobe 插件：apl (appendToList)

{{plug-in}}

`apl` 插件允许您安全地向已列表分隔的变量（如 [`events`](../page-vars/events/events-overview.md)、[`linkTrackVars`](../config-vars/linktrackvars.md)、[`list`](../page-vars/list.md) 和其他变量）添加新值。

* 如果要添加的值在变量中不存在，则代码会将该值添加到字符串的结尾。
* 如果要添加的值在变量中已存在，则此插件不会更改该值。此功能可让您的实施避免出现重复的值。
* 如果要添加到的变量为空，则插件会将该变量设置为新值。

如果要向现有变量添加新值，并且现有变量包含由分隔值构成的字符串，Adobe 建议使用此插件。如果您要为包含分隔值的变量连接字符串，则不需要使用此插件。

## 使用Web SDK或Web SDK扩展安装此插件

尚不支持使用此插件在Web SDK中使用。

## 使用Adobe Analytics扩展安装此插件

Adobe提供了一个扩展，通过该扩展，您可以将最常用的插件与Adobe Analytics结合使用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]按钮
1. 安装并发布[!UICONTROL 常用 Analytics 插件]扩展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化 APL（附加到列表）
1. 保存并发布对上述规则所做的更改。

## 使用自定义代码编辑器安装此插件

如果您不想使用“常用Analytics插件”插件扩展，则可以使用自定义代码编辑器。

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
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`apl` 函数使用以下参数：

* **`lv`**（必需，字符串）：包含要向其添加新值的已分隔列表的变量
* **`vta`**（必需，字符串）：要添加到 `lv` 参数值的以逗号分隔的新值列表。
* **`d1`**（可选，字符串）：用于分隔已包含在 `lv` 参数中的各个值的分隔符。如果未设置，则将默认使用逗号 (`,`)。
* **`d2`**（可选，字符串）：输出分隔符。如果未设置，则默认值与 `d1` 的值相同。
* **`cc`**（可选，布尔值）：指示是否使用区分大小写检查的标志。如果为 `true`，则重复检查区分大小写。如果为 `false` 或未设置，则重复检查不区分大小写。默认为 `false`。

`apl` 函数会返回 `lv` 参数的值以及 `vta` 参数中的任何非重复值。

## 示例

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## 版本历史记录

### 4.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

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

* 现在使用 `inList` 函数进行比较处理

### 2.0（2016 年 1 月 26 日）

* `d`（分隔符）参数现在为可选参数（默认为逗号）
* `u`（区分大小写标记）参数现在为可选参数（默认为不区分大小写）
* 无论 `u`（区分大小写标记）参数为何值，如果该值已存在于列表中，则插件都不会再向列表附加值
