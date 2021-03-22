---
title: formatTime
description: 将秒数转换为以分钟、小时等为单位的等效值。
translation-type: tm+mt
source-git-commit: 56b21b6acb948c478d7b2a29c3e8375a8fe77ce2
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 99%

---


# Adobe 插件：formatTime

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`formatTime` 插件允许您获取任意秒数，并在四舍五入到所需的基准值后以存储段格式提供它们。如果您希望以秒为单位捕获时间值并将其转换为存储段格式（如分钟、天或周），Adobe 建议使用此插件。如果您不想将基于秒的值存储为时间舍入格式，则不需要使用此插件。

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
   * 操作类型：初始化 formatTime
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
/* Adobe Consulting Plugin: formatTime v2.0 */
function formatTime(ns,tf,bml){var f=ns,d=tf,e=bml;function h(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(arguments&&"-v"===arguments[0])return{plugin:"formatTime",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.formatTime="2.0");if(!("undefined"===typeof f||isNaN(f)||0>Number(f))){b="";if("string"===typeof d&&"d"===d||("string"!==typeof d||!h("h,m,s",d))&&86400<=f){var c=86400;var g="days";b=isNaN(e)?1:c/(e*c)}else"string"===typeof d&&"h"===d||("string"!==typeof d||!h("m,s",d))&&3600<=f?(c=3600,g="hours",b=isNaN(e)?4:c/(e*c)):"string"===typeof d&&"m"===d||("string"!==typeof d||!h("s",d))&&60<=f?(c=60,g="minutes",b=isNaN(e)?2:c/(e*c)):(c=1,g="seconds",b=isNaN(e)?.2:c/e);b=Math.round(f*b/c)/b+" "+g;0===b.indexOf("1 ")&&(b=b.substring(0,b.length-1));return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`formatTime` 方法使用以下参数：

* **`ns`**（必需，整数）：要转换或格式化的秒数
* **`tf`**（可选，字符串）：要返回秒的格式类型；默认为秒
   * 如果您希望以天为单位显示时间，则可将其设置为 `"d"`（默认情况下，舍入到以 1/4 天为基准所得出的最近值）
   * 如果您希望以小时为单位显示时间，则可将其设置为 `"h"`（默认情况下，舍入到以 1/4 小时为基准所得出的最近值）
   * 如果您希望以分钟为单位显示时间，则可将其设置为 `"m"`（默认情况下，舍入到以 1/2 分钟为基准所得出的最近值）
   * 如果您希望以秒为单位显示时间，则可将其设置为 `"s"`（默认情况下，舍入到以 5 秒为基准所得出的最近值）
* **`bml`**（可选，数字）：舍入基准的长度。默认为 `tf` 参数中列出的基准值

该方法会返回使用 `tf` 参数中指定的单位进行格式化的秒数。如果未设置 `tf` 参数：

* 若返回值小于 1 分钟，则将以“5 秒”为基准四舍五入到最接近的值
* 若返回值介于 1 分钟和 1 小时之间，则将以“0.5 分钟”为基准四舍五入到最接近的值
* 若返回值介于 1 小时和 1 天之间，则将以“0.25 小时”为基准四舍五入到最接近的值
* 若返回值大于 1 天，则将以“1 天”为基准四舍五入到最接近的值

## 示例

### 示例 1

以下代码...

```js
s.eVar1 = s.formatTime(38242);
```

...将 s.eVar1 设置为等于“10.5 小时”

传入的参数（38242 秒）等于 10 小时 37 分钟 22 秒。由于此调用中未设置 tf 参数，且传入的秒数介于 1 小时和 1 天之间，因此插件将返回已转换为以四分之一小时为基准所得出的最近值的秒数。

### 示例 2

以下代码...

```js
s.eVar1 = s.formatTime(38250);
```

...将 s.eVar1 设置为等于“10.75 小时”传入的参数（38250 秒）等于 10 小时 37 分钟 30 秒。在这种情况下，如果将传入的秒数舍入到以四分之一小时为基准所得出的最近值，则会将最终值设置为 10.75 小时

### 示例 3

以下代码...

```js
s.eVar1 = s.formatTime(38242, "m");
```

...将 s.eVar1 设置为等于“637.5 分钟”

在这种情况下，“m”参数会强制插件将秒数转换为以 1/2 分钟为基准所得出的最近值

### 示例 4

以下代码...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...将 s.eVar1 设置为等于“640 分钟”

tf 参数值（“m”）会强制插件将秒数转换为分钟数，但 bml 参数值 (20) 也会强制插件将分钟数转换为以 20 分钟为基准所得出的最近值。

### 示例 5

以下代码...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...将 s.eVar1 设置为等于“126 秒”，这是以 2 秒为基准时所得出的最接近 125 秒的结果

### 示例 6

以下代码...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...将 s.eVar1 设置为等于“3 分钟”，这是以 3 分钟为基准时所得出的最接近 125 秒的结果

### 示例 7

以下代码...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...将 s.eVar1 设置为等于“2.4 分钟”，这是以 2/5 分钟为基准（例如，.4 = 2/5）时所得出的最接近 145 秒的结果

## 版本历史记录

### 2.0（2021年3月19日）

* 已添加版本号作为上下文数据。

### 1.1（2018 年 5 月 21 日）

* 添加了 `bml` 参数，以便在舍入方面更灵活

### 1.0（2018 年 4 月 15 日）

* 第一版。
