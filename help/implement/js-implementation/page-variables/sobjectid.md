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


# s_objectID

该变量是一个全局变量，应在链接的 [!UICONTROL onClick] 事件中设置。

<!-- 

s_objectID.xml

 -->

通过为链接或页面上的链接位置创建唯一对象 ID，您可以改善访客活动跟踪功能，或使用 [!UICONTROL Activity Map]（而非链接 URL）来报告链接类型或位置。

> [!NOTE] 将s_objectID与Activity Map一起使用时，需要以分号(;) [结尾](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html)。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | OID | [!UICONTROL Activity Map]、[!UICONTROL ClickMap] | 点击链接的绝对 URL |

使用 *`s_objectID`* 的常见原因有三个：

* 为了整合一天内经常发生变化的访客活动。
* 为了分离 [!UICONTROL Activity Map] 组合在一起的链接活动。
* 为了提高 [!UICONTROL Activity Map] 数据报告的准确性。

**汇总高度动态链接的点击** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

如果您的网站是高度动态的，并且某些页面上的链接在一天里会有所变化，则可以使用 *`s_objectID`* 来标识页面上链接的位置。例如，如果将 *`s_objectID`* 设置为“左上 1”或“左上 2”（表示页面左上方的第一个链接），则该位置显示的所有链接（或将 *`s_objectID`* 设置为相同值的链接）都将与访客点击图一起报告。如果不使用 *`s_objectID`*，虽然可以查看点击特定链接的次数，但无法深入分析访客如何在网站中使用该位置的所有其他链接。

**区分整合的点击** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

如果您网站上的 *`pageName`* 变量用于显示访客正在查看的部分或模板，而不是访客正在查看的特定页面，则您可能需要使用 *`s_objectID`* 来分隔出现在该页面模板多个版本上的链接。例如，如果您有一个适用于网站中所有产品的模板页面，可能在所有页面上都会有一个指向主页和指向模板中搜索框的链接。若要按单个产品（而非模板）了解这些链接的使用情况，您可以使用产品特定的值填充&#x200B;*`s_objectID`*，例如“prod 123789 home page”或“prod 123789 search”。完成后，[!UICONTROL Activity Map] 会按照各个产品报告这些链接。

**提高[!UICONTROL Activity Map]准确性** {#section_08B3406821294DCCABEEB99C90CF5C52}

在某些情况下，访客点击图不会报告除 Internet Explorer、Firefox、Netscape、Opera 和 Safari 以外的浏览器。尽管其他浏览器所占的比例很小，但确实存在一部分点击量和其他量度。使用链接中的 *`s_objectID`* 对地址进行唯一标识可解决浏览器报告问题。以下示例介绍了如何使用 *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**语法和可能值** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID 可以包含任何文本标识符。

```js
s_objectID="unique_id" 
```

*`s_objectID`* 变量除标准变量限制以外，无其它限制。

**示例** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**配置设置** {#section_95396657D55B41ECB66B83D0534EA827}

无
