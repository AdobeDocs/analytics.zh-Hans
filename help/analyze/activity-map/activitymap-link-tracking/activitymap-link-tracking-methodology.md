---
description: 这部分内容主要面向 Adobe Analytics 管理员。关注的重点是新的链接跟踪参数，以及这些参数如何确保链接在各种浏览器和设备上的唯一性和一致性，以及如何更好地处理链接在页面上的位置变换。
title: 链接跟踪方法
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: 业务从业者，管理员
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 96%

---


# 链接跟踪方法

这部分内容主要面向 Adobe Analytics 管理员。关注的重点是新的链接跟踪参数，以及这些参数如何确保链接在各种浏览器和设备上的唯一性和一致性，以及如何更好地处理链接在页面上的位置变换。

>[!IMPORTANT]
>
>其文本（非 href）可能包含 PII（个人身份识别信息）的任何链接，均应使用 [s_objectID](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/vars/page-vars/page-variables.html) 或通过以 [s.ActivityMap.linkExclusions 或 s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars) 排除 ActivityMap 链接收集的方式进行显式实施。有关 Activity Map 如何收集 PII 数据的更多信息，请转至[此处](/help/analyze/activity-map/lnk-tracking-overview.md)。

Activity Map 根据以下两个 ID 进行链接跟踪：

* 主 ID：这是链接的可识别参数。
* 链接区域：这是次要参数，允许用户指定一个代表页面内或区域内整个链接区域的的字符串。如果用户没有提供此参数，此参数则会自动生成。

## 主 ID  {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

如果 HTML 拥有 s_objectid，则默认情况下，主 ID 就是 s_objectid。否则，以下参数将作为主 ID（按照下面的优先顺序）：

* Innertext
* Alttext
* 标题
* Src
* Action

## 使用 InnerText 与使用链接操作 (URL) 的对比  {#section_70C3573E22274522A8CC035BF18EC468}

链接操作是指单击链接时网页所采取的操作 - 通常是指单击链接后访问的 URL。使用链接操作时，可能会遇到以下一些问题：

* 两个或多个不同的链接拥有相同的 ID
* 链接的可读性
* 一个链接包含多项操作（取决于您查看链接时使用的设备）

因此，与使用链接操作 (URL) 相比，使用 InnerText 具备以下优势：

* 能够较好地代表链接标识。主 ID 重复的现象显著减少，因为很少会出现多个链接包含相同文本的情况。
* 能够确保主 ID 在各类设备和浏览器中保持一致性。
* 不会因链接在页面上变换位置而受到影响。
* 能够提高可读性，因此用户在 Activity Map 之外就可以开始分析链接跟踪报表。

## 链接区域 {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

这个新增的属性允许用户指定一个能够代表链接所在页面区域的字符串。

例如，针对位于网页菜单区域的“联系我们”链接而言，用户可能希望传递“Menu”区域参数。同样地，针对位于网页页脚的“联系我们”链接，可能需要将区域参数设置为“footer”。

“链接区域”值并非设置在链接中，而是设置在包含该区域的 DOM HTML 树上的一个 HTML 元素中。使用“链接区域”具备以下优势：

* 有助于区分具有相同主 ID 的链接。
* 区域中的趋势不太会受到网页上动态方面的影响。
* 用户可以看到区域内表现最佳的链接。以“区域”作为锚点，我们可以显示当前在页面中不可见的链接所对应的叠加图（Ajax，定位）。
* “区域”可以取代页面，成为可以在多个网页中使用的特定区域。它有助于解答这样的问题：“我的‘产品供应’区域在女性登录页面表现最佳，还是在男性登录页面表现最佳？”
* 就其本身而言，区域是用于分析高度动态网页的相关维度。这是因为它能够消除由于不断变化的链接所带来的干扰信息：CNN 登录页面的“最新消息”区域可能会有很多不断变化的链接。但是区域始终不变。所以在区域的层面上，表现数日范围内的趋势可能会很有吸引力。

**自定义区域跟踪**

您可以自定义链接的区域参数（默认为链接 ID）：一个设置为“ID”的标签将会把所有包含“id”参数的 HTML 元素作为一个区域。因此，将区域标签设置为“id”很可能会返回大量不同的区域（页面上有多少个不同的“ID”，就会返回多少个不同的区域）。或者，如果您希望实现更具定制化的效果，则可以将区域标签设置得更加具体，例如“region_id”。

您可以在下方看到一些 HTML 样例，均使用默认区域 ID 属性“id”。

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

如果您愿意，可以使用任意字符串标识符来标记元素，在本例中使用的是“lpos”，然后添加名为“lpos”的属性。

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## 配置变量 {#configuration-vars}

请注意，下面列出的变量仅供参考。您应该不拘一格，正确地配置 Activity Map，但是您可以使用这些变量来自定义您的实现。

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量名称 </th> 
   <th colname="col2" class="entry"> 示例 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionIDAttribute </td> 
   <td colname="col2"> 默认为“id”参数。您可以将此变量设置为其他参数。 </td> 
   <td colname="col3"> 字符串，可以将来自 s.linkObject 某些上级（父级、父级的父级...）元素（例如<b>被单击的元素</b>）的标签属性用作区域 ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.link </td> 
   <td colname="col2"> 
    <code>//&nbsp;only&nbsp;ever&nbsp;use&nbsp;"title"&nbsp;attributes&nbsp;from&nbsp;A&nbsp;tags</code><br/>
    <code>function(clickedElement)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;linkId;</code><br/>
    <code>&nbsp;&nbsp;if&nbsp;(clickedElement&nbsp;&amp;&amp;&nbsp;clickedElement.tagName.toUpperCase()&nbsp;===&nbsp;'A')&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;linkId&nbsp;=&nbsp;clickedElement.getAttribute('title');</code><br/>
    <code>&nbsp;&nbsp;}</code><br/>
    <code>&nbsp;&nbsp;return&nbsp;linkId;</code><br/>
    <code>}</code> </td>
   <td colname="col3"> 函数，可以收到被单击的 HTMLElement，且应该返回代表<b>被单击的链接</b>的字符串值。<br/>
      <br/>
     如果返回值为false（null、undefined、空字符串、0），则不跟踪任何链接。 </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.region </td> 
   <td colname="col2"> 
        <code>//&nbsp;only&nbsp;ever&nbsp;use&nbsp;lowercase&nbsp;version&nbsp;of&nbsp;tag&nbsp;name&nbsp;concatenated&nbsp;with&nbsp;first&nbsp;className&nbsp;as&nbsp;the&nbsp;region</code><br/>
    <code>function(clickedElement)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;regionId,&nbsp;className;</code><br/>
    <code>&nbsp;&nbsp;while&nbsp;(clickedElement&nbsp;&amp;&amp;&nbsp;(clickedElement&nbsp;=&nbsp;clickedElement.parentNode))&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;regionId&nbsp;=&nbsp;clickedElement.tagName;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;if&nbsp;(regionId)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;regionId.toLowerCase();</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;}</code><br/>
    <code>&nbsp;&nbsp;}</code><br/>
    <code>}</code> </td> 
   <td colname="col3"> 函数，可以被单击的 HTMLElement，且应该返回代表<b>链接被单击时所在的区域</b>的字符串值。<br/>
      <br/>
     如果返回值为false（null、undefined、空字符串、0），则不跟踪任何链接。 </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
     <code>//&nbsp;Exclude&nbsp;links&nbsp;tagged&nbsp;with&nbsp;a&nbsp;special&nbsp;linkExcluded&nbsp;CSS&nbsp;class</code><br/>
    <code>&lt;style&gt;</code><br/>
    <code>.linkExcluded&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;display:&nbsp;block;</code><br/>
    <code>&nbsp;&nbsp;height:&nbsp;1px;</code><br/>
    <code>&nbsp;&nbsp;left:&nbsp;-9999px;</code><br/>
    <code>&nbsp;&nbsp;overflow:&nbsp;hidden;</code><br/>
    <code>&nbsp;&nbsp;position:&nbsp;absolute;</code><br/>
    <code>&nbsp;&nbsp;width:&nbsp;1px;</code><br/>
    <code>}</code><br/>
    <code>&lt;/style&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;link&nbsp;does&nbsp;not&nbsp;have&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.&nbsp;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link1&lt;/span&gt;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link2&lt;/span&gt;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;script&gt;</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid');</code><br/>
    <code>&nbsp;&nbsp;s.ActivityMap.linkExclusions&nbsp;=&nbsp;'exclude-link1,exclude-link2';</code><br/>
    <code>&lt;/script&gt;</code> </td> 
   <td colname="col3"> 字符串，可接收以逗号分隔的字符串列表，以便在链接文本中进行搜索。如果找到，则链接不会由 Activity Map 跟踪。如果未设置，则不会尝试停止由 Activity Map 跟踪链接。 </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>//&nbsp;Exclude&nbsp;regions&nbsp;on&nbsp;the&nbsp;page&nbsp;from&nbsp;its&nbsp;links&nbsp;being&nbsp;trackable&nbsp;by&nbsp;ActivityMap</code><br/>
    <code>&lt;div&nbsp;id="links-included"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;but&nbsp;does&nbsp;not&nbsp;match&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;/a&gt;</code><br/>
    <code>&lt;/div&gt;</code><br/>
    <code>&lt;div&nbsp;id="links-excluded"&gt;&nbsp;</code><br/>
    <code>&nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;matches&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;/a&gt;</code><br/>
    <code>&lt;/div&gt;</code><br/>
    <code>&lt;script&gt;</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid');</code><br/>
    <code>&nbsp;&nbsp;s.ActivityMap.regionExclusions&nbsp;=&nbsp;'links-excluded';</code><br/>
    <code>&lt;/script&gt;</code> </td> 
   <td colname="col3"> 字符串，可接收以逗号分隔的字符串列表，以便在区域文本中进行搜索。如果找到，则链接不会由 Activity Map 跟踪。如果未设置，则不会尝试停止由 Activity Map 跟踪链接。 </td>
  </tr>
 </tbody>
</table>
