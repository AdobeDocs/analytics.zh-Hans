---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# 列表属性

列表属性是一种分隔的值列表，这些值被传入到一个变量，然后作为单独的行项目进行报告。列表属性通常在包含用户可选值的页面上实施，例如，具有复选框或单选按钮的列表项目。当您希望在不发送多个图像请求的情况下，在一个变量中定义多个值时，这些列表属性非常有用。

<!-- 

list_props.xml

 -->

**注意事项**

* 列表属性只在流量变量启用 ([props](/help/implement/js-implementation/c-variables/page-variables.md))。
* 无法为列表属性启用路径分析和关联。
* Analytics 几乎为每个报表（包括所有列表属性报表）都提供了访问和独特访客。
* 列表属性支持分类。
* 任何自定义流量变量都可成为一个列表属性。（例外：[pageName](/help/implement/js-implementation/c-variables/page-variables.md)、[channel](/help/implement/js-implementation/c-variables/page-variables.md) 和 [server](/help/implement/js-implementation/c-variables/page-variables.md)。）

* 在同一个图像请求中定义重复值时，不会删除重复实例。

可以通过启用“列表支持”并选择分隔符，在“管理工具”&gt;“报表包”&gt;“流量变量”页面将属性更改为列表属性。常用的分隔符包括冒号、分号、逗号或竖线。从技术上讲，分隔符可以是头 127 个 ASCII 字符中的任意一个。

**实施示例** {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

在请求启用列表属性时，请指明您要使用的分隔符。在启用了您选择的&#x200B;*`s.prop`*&#x200B;之后，可在变量中设置多个值，如以下示例中所示：

由竖线分隔的列表属性，传入两个值：

```js
s.prop1="Banner ad impression|Sidebar impression"
```

由逗号分隔的列表属性，传入多个值：

```js
s.prop2="cerulean,vermilion,saffron"
```

列表属性还可随单个值一起发送：

```js
s.prop3="Single value"
```

分隔符可随时更改。但是，实施必须匹配新的分隔符。如果未使用正确的分隔符，则会导致列表属性值在报表中被视为一个包含若干字符串的行项目。

由于列表属性仍是一个流量变量，因此它必须遵守流量变量的限制。列表属性的数据被限定为 100 字节，并且受区分大小写设置影响。

