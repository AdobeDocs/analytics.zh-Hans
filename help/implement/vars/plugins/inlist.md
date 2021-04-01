---
title: inList
description: 检查某个值是否包含在另一个字符分隔的值中。
translation-type: ht
source-git-commit: 27d151abe9bdf52c6eabdc3e9c785a99d08f971e
workflow-type: ht
source-wordcount: '743'
ht-degree: 100%

---


# Adobe 插件：inList

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`inList` 插件允许您检查某个值是否已存在于一个分隔字符串或 JavaScript 数组对象中。有一些其他插件需要 `inList` 插件才能正常运行。与 JavaScript 方法 `indexOf()` 相比，此插件具有一个明显的优势，即它不会匹配部分字符串。例如，如果您使用此插件检查 `"event2"`，则此插件不会匹配包含 `"event25"` 的字符串。如果您不需要检查分隔字符串或数组中的值，或者如果您要使用自己的 `indexOf()` 逻辑，则无需使用此插件。

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
   * 操作类型：初始化 inList
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
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`inList` 方法使用以下参数：

* **`lv`**（必需，字符串或数组）：要搜索的值分隔列表或 JavaScript 数组对象
* **`vtc`**（必需，字符串）：要搜索的值
* **`d`**（可选，字符串）：用于分隔 `lv` 参数中各个值的分隔符。如果未设置，则将默认使用逗号 (`,`)。
* **`cc`**（可选，布尔）：如果设置为 `true`，则在检查时会区分大小写。如果设置为 `false` 或忽略，则会在检查不会区分大小写。默认为 `false`。

调用此方法时，如果找到匹配项，则将返回 `true`；如果找不到匹配项，则将返回 `false`。

## 示例调用

### 示例 1

如果...

```js
s.events="event22,event24";
```

...并运行以下代码...

```js
if(s.inList(s.events,"event22"))
```

...if 条件语句将为 true

### 示例 2

如果...

```js
s.events="event22,event24";
```

...并运行以下代码...

```js
if(s.inList(s.events,"event2"))
```

...if 条件语句将为 false，因为 inList 调用在 event2 与 s.events 中的任何分配值之间未找到精确匹配项

### 示例 3

如果...

```js
s.events="event22,event24";
```

...并运行以下代码...

```js
if(!s.inList(s.events,"event23"))
```

...if 条件语句将为 true，因为 inList 调用在 event23 与 s.events 中的任何分配值之间未找到精确匹配项（请注意 inList 变量调用开头的“NOT”运算符）。

### 示例 4

如果...

```js
s.events = "event22,event23";
```

...并运行以下代码...

```js
if(s.inList(s.events,"EVenT23","",1))
```

...if 条件语句将为 false。尽管此示例不太符合实际，但它可以表明在使用区分大小写的标志时需要谨慎。

### 示例 5

如果...

```js
s.linkTrackVars = "events,eVar1";
```

...并运行以下代码...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...if 条件语句将为 false。传递到调用的 d 参数的值（即 &quot;|&quot;）会假定 s.linkTrackVars 中的各个值以管道字符分隔，而实际上，这些值以逗号分隔。在这种情况下，此插件将尝试在 s.linkTrackVars 的完整值（即 &quot;events,eVar1&quot;）与要查找的值（即 &quot;eVar1&quot;）之间进行匹配。

## 版本历史记录

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### v2.1（2019 年 9 月 26 日）

* 添加了将 `cc` 参数设为非布尔值的选项。例如，`1` 是有效的示例检查值。

### v2.0（2018 年 4 月 17 日）

* 修正版本（重新编译，代码更小）。

### v1.01（2017 年 9 月 27 日）

* 优化了代码，以减小代码大小

### v1.0（2009 年）

* 第一版。


