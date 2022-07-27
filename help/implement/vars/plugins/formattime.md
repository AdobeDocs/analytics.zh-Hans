---
title: formatTime
description: 将秒数转换为以分钟、小时等为单位的等效值。
feature: Variables
exl-id: 4b98e7fe-f05b-4346-b284-697268adc1a2
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 97%

---

# Adobe 插件：formatTime

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`formatTime` 插件允许您获取任意秒数，并在四舍五入到所需的基准值后以存储段格式提供它们。如果您希望以秒为单位捕获时间值并将其转换为存储段格式（如分钟、天或周），Adobe 建议使用此插件。如果您不想将基于秒的值存储为时间舍入格式，则不需要使用此插件。

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
    * Action Type: Initialize formatTime
1. Save and publish the changes to the rule.-->

## 使用自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) 使用您的Adobe ID凭据。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
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

`formatTime` 函数使用以下参数：

* **`ns`**（必需，整数）：要转换或格式化的秒数
* **`tf`**（可选，字符串）：要返回秒的格式类型；默认为秒
   * 如果您希望以天为单位显示时间，则可将其设置为 `"d"`（默认情况下，舍入到以 1/4 天为基准所得出的最近值）
   * 如果您希望以小时为单位显示时间，则可将其设置为 `"h"`（默认情况下，舍入到以 1/4 小时为基准所得出的最近值）
   * 如果您希望以分钟为单位显示时间，则可将其设置为 `"m"`（默认情况下，舍入到以 1/2 分钟为基准所得出的最近值）
   * 如果您希望以秒为单位显示时间，则可将其设置为 `"s"`（默认情况下，舍入到以 5 秒为基准所得出的最近值）
* **`bml`**（可选，数字）：舍入基准的长度。默认为 `tf` 参数中列出的基准值

此函数将返回使用 `tf` 参数中指定的单位进行格式化的秒数。如果未设置 `tf` 参数：

* 若返回值小于 1 分钟，则将以“5 秒”为基准四舍五入到最接近的值
* 若返回值介于 1 分钟和 1 小时之间，则将以“0.5 分钟”为基准四舍五入到最接近的值
* 若返回值介于 1 小时和 1 天之间，则将以“0.25 小时”为基准四舍五入到最接近的值
* 若返回值大于 1 天，则将以“1 天”为基准四舍五入到最接近的值

## 示例

```js
// Sets eVar1 to "10.5 hours".
// 38242 seconds equals 10 hours, 37 minutes, and 22 seconds. Since the tf argument is not set, the value returned is the number of seconds converted to the nearest quarter-hour benchmark.
s.eVar1 = formatTime(38242);

// Sets eVar4 to "10.75 hours".
// 38250 seconds equals 10 hours, 37 minutes, and 30 seconds. This value rounds up to the nearest quarter hour.
s.eVar4 = formatTime(38250);

// Sets eVar9 to "637.5 minutes".
s.eVar9 = formatTime(38242, "m");

// Sets eVar14 to "640 minutes".
// The tf argument forces the returned value to minutes, while the bml argument forces the value to the nearest 20-minute increment.
s.eVar14 = formatTime(38242, "m", 20);

// Sets eVar2 to "126 seconds", the closest 2-second benchmark to 125 seconds.
s.eVar2 = formatTime(125, "s", 2);

// Sets eVar7 to "3 minutes", the closest 3-minute benchmark to 125 seconds.
s.eVar7 = formatTime(125, "m", 3);

// Sets eVar55 to "2.4 minutes, the closest 2/5-minute benchmark to 145 seconds.
s.eVar55 = formatTime(145, "m", .4);
```

## 版本历史记录

### 2.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 1.1（2018 年 5 月 21 日）

* 添加了 `bml` 参数，以便在舍入方面更灵活

### 1.0（2018 年 4 月 15 日）

* 第一版。
