---
description: 显示访客在进入网站前所在的域或 URL、访客找到网站的方法、以及经由这些反向链接位置对您网站的访问次数。
seo-description: 显示访客在进入网站前所在的域名或 URL、访客找到网站的方法、以及经由这些反向链接位置对您的网站的访问次数。
seo-title: 反向链接
solution: Analytics
title: 反向链接
topic: 报表
uuid: e63b47b4-49f3-43af-8409-3272bec0484e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 反向链接

显示访客在进入网站前所在的域或 URL、访客找到网站的方法、以及经由这些反向链接位置对您网站的访问次数。

例如，如果访客点击网站 A 上的链接后转至您的网站，则网站 A 为反向链接（如果它未定义为属于您的域）。在实施过程中，实施顾问会帮助您定义属于您的网站的域和 URL。（此更改可在实施后完成。）

域和 URL 如果不属于这些定义的对象则会被视为反向链接。例如，网页 A 和网页 B 都被添加到内部 URL 过滤器中，但是网页 C 没有。在这种情况下，网页 C 被视为反向链接。

## 分配、过期和特殊值 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Marketing Reports &amp; Analytics (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 量度分配 </td> 
   <td colname="col2"> “最近” </td> 
   <td colname="col3"> “最近” </td> 
   <td colname="col4"> “最近” </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值过期时间 </td> 
   <td colname="col2"> 访问 </td> 
   <td colname="col3"> 访问 </td> 
   <td colname="col4"> 访问 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值限制 </td> 
   <td colname="col2"> 无限制（后续版本中或有变更） </td> 
   <td colname="col3"> 无限制（后续版本中或有变更） </td> 
   <td colname="col4"> 无 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特殊值 </td> 
   <td colname="col2"> <p>“无”：整个网站范围内，在访问期间没有反向链接的总计数。 </p> </td> 
   <td colname="col3"> <p>“无”：整个网站范围内，在访问期间没有反向链接的总计数。 </p> </td> 
   <td colname="col4"> <p> 空：等于“无”，整个网站范围内，在访问期间没有反向链接的总计数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 注释 {#section_B83A3571D64E4E7792712FAF740D7955}

* 反向链接、反向链接类型和反向链接域名会在首次访问点击时设置，或者当反向链接来自外部时，在访问期间设置（例如，如果访客离开网站，使用搜索引擎，然后在第一次访问过期之前回到网站）。这些值会同时设置，并在整个访问期间存在。
* 内部 URL 会被过滤。只有与内部 URL 过滤器不匹配的反向链接才会出现在此报表中。
* 在 Ad Hoc Analysis 中，对应的量度称为“反向链接实例”。
* “键入/书签”值未包括在反向链接报表中。这表示网站范围的访问数与此报表中的访问数不匹配。

## 报表历史记录 {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 更改 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2014 年 1 月 16 日 </td> 
   <td colname="col2"> Data Warehouse 已更新，以匹配 Marketing Reports &amp; Analytics 所用的逻辑。在此日期之前，搜索关键词在整个访问期间并非持续存在。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2012 年 6 月 19 日 </td> 
   <td colname="col2"> <p> 在 2012 年 7 月之前，“无”包括所有移动流量、键入/书签和没有 JavaScript 的所有访问数。在 2012 年 7 月之后，“无”仅包括访问的首个页面上没有 JavaScript 的点击数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

