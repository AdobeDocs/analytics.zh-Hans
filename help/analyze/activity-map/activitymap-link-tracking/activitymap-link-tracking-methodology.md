---
description: 这部分内容主要面向 Adobe Analytics 管理员。关注的重点是新的链接跟踪参数，以及这些参数如何确保链接在各种浏览器和设备上的唯一性和一致性，以及如何更好地处理链接在页面上的位置变换。
seo-description: 这部分内容主要面向 Adobe Analytics 管理员。关注的重点是新的链接跟踪参数，以及这些参数如何确保链接在各种浏览器和设备上的唯一性和一致性，以及如何更好地处理链接在页面上的位置变换。
seo-title: 链接跟踪方法
solution: Analytics
title: 链接跟踪方法
topic: Activity Map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# 链接跟踪方法

这部分内容主要面向 Adobe Analytics 管理员。关注的重点是新的链接跟踪参数，以及这些参数如何确保链接在各种浏览器和设备上的唯一性和一致性，以及如何更好地处理链接在页面上的位置变换。

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) or by excluding ActivityMap link collection with [s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions](../../../analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#section_634197EACD404AC086DF9A03B813C8C3). 有关 Activity Map 如何收集 PII 数据的更多信息，请转至[此处](../../../analyze/activity-map/lnk-tracking-overview.md#section_A9F016E64F33446F8916855D8C69A7C6)。

Activity Map 根据以下两个 ID 进行链接跟踪：

* 主 ID：这是链接的可识别参数。
* 链接区域：这是次要参数，允许用户指定一个代表页面内或区域内整个链接区域的的字符串。如果用户没有提供此参数，此参数则会自动生成。

## 主 ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

如果 HTML 拥有 s_objectid，则默认情况下，主 ID 就是 s_objectid。否则，以下参数将作为主 ID（按照下面的优先顺序）：

* Innertext
* Alttext
* Title
* Src
* Action

## 使用 InnerText 与使用链接操作 (URL) 的对比 {#section_70C3573E22274522A8CC035BF18EC468}

链接操作是指单击链接时网页所采取的操作 - 通常是指单击链接后访问的 URL。使用链接操作时，可能会遇到以下一些问题：

* 两个或多个不同的链接拥有相同的 ID
* 链接的可读性
* 一个链接包含多项操作（取决于您查看链接时使用的设备）

因此，与使用链接操作 (URL) 相比，使用 InnerText 具备以下优势：

* 能够较好地代表链接标识。主 ID 重复的现象显著减少，因为很少会出现多个链接包含相同文本的情况。
* 能够确保主 ID 在各类设备和浏览器中保持一致性。
* 不会因链接在页面上变换位置而受到影响。
* 能够提高可读性，因此用户在 Activity Map 之外就可以开始分析链接跟踪报表。

## Link region {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

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
s.ActivityMap.regionIDAttribute="lpos"; 
   
<div id="nav" lpos="navbar"> 
  <ul> 
     <li> Menu Category A 
    <ul> 
      <li><a href="">Menu Item A 1</a> 
      <li><a href="">Menu Item A 2</a> 
     </ul> 
    </li> 
     <li> Menu Category B 
     <ul> 
      <li><a href="">Menu Item B 1</a>  
      <li><a href="">Menu Item B 2</a> 
  
   </ul> 
</ul> 
</div> 
  
<div id="content" > 
  <div id="breaking_news" lpos="breaking_news> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
</div>
```

## Configuration variables {#section_634197EACD404AC086DF9A03B813C8C3}

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
   <td colname="col1"> s. ActivityMap. regionIDAttribute </td> 
   <td colname="col2"> 默认为“id”参数。您可以将此变量设置为其他参数。 </td> 
   <td colname="col3"> 字符串，可以将来自 s.linkObject 某些上级（父级、父级的父级...）元素（例如<b>被单击的元素</b>）的标签属性用作区域 ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. ActivityMap. link </td> 
   <td colname="col2"> 
    <code>//只能使用A标记函数(ClickedElement){var LinkID中的“title”属性；if(clickedElement&amp;&amp; ClickedElement. TagName. toUpperCase()==='A'){linkID= clickedElement. getAttribute('title')；}返回linkID；}} </code>
  </td> 
   <td colname="col3"> 函数，可以收到被单击的 HTMLElement，且应该返回代表<b>被单击的链接</b>的字符串值。 <p>如果返回值为 false（空、未定义、空字符串、0），则表示没有跟踪任何链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. ActivityMap. region </td> 
   <td colname="col2"> 
    <code>//仅在使用第一个className作为区域函数(ClickedElement){var RegionID，ClassName时使用第一个className的小写版本。while(clickedElement&amp;&amp;(clickedElement= clickedElement. parentNode)){regionID= clickedElement. tagName；if(regionID){return RegionID. toLoverCase()；}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}} </code>
  </td> 
   <td colname="col3"> 函数，可以被单击的 HTMLElement，且应该返回代表<b>链接被单击时所在的区域</b>的字符串值。 <p>如果返回值为 false（空、未定义、空字符串、0），则表示没有跟踪任何链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>//排除使用特殊链接排除的CSS类&lt;样式&gt;. linkExcluded{显示标记的链接：块；高度：px；left：-9999px；溢出：隐藏；位置：绝对；宽度：px；}&lt;/style&gt;&lt; a href="next-page.html"&gt;链接被跟踪，因为链接没有与过滤器匹配的隐藏文本。&lt;/a&gt;&lt; a href="next-page.html"&gt;链接未跟踪，因为s. ActivityMap. linkExclusions已设置，且此链接具有与筛选器匹配的隐藏文本。&lt; span class=“linkExcluded”&gt; excluding-link1&lt;/span&gt;&lt;/a&gt;&lt; a href=“next-page.html”&gt;“链接”未跟踪，因为s. ActivityMap. linkExclusions已设置，且此链接具有与过滤器相匹配的隐藏文本。 &lt;span class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>字符串，可接收以逗号分隔的字符串列表，以便在链接文本中进行搜索。如果找到，则链接不会由 Activity Map 跟踪。如果未设置，则不会尝试停止由 Activity Map 跟踪链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>//由于s. ActivityMap. regionExclusions已设置但与筛选器不匹配，因此会跟踪通过ActivityMap&lt; div id=“links-included”&gt;&lt; a href=“next-page.html”&gt;“链接”跟踪页面上页面上的区域。&lt;/a&gt;&lt;/div&gt;&lt; div id=“links-excluded”&gt;&lt; a href=“next-page.html”&gt;&gt;“链接”，因为s. ActivityMap. regionExclusions已设置，且此链接与过滤器相匹配。&lt;/a&gt; &lt;/div&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.regionExclusions = 'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>字符串，可接收以逗号分隔的字符串列表，以便在区域文本中进行搜索。如果找到，则链接不会由 Activity Map 跟踪。如果未设置，则不会尝试停止由 Activity Map 跟踪链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>
