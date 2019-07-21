---
description: 按网站上网页收到的最大流量对页面进行排名。如果您的业务问题涉及页面的量化数据，那么您可通过添加正确的量度来使用此报表解决该问题。
seo-description: 按网站上网页收到的最大流量对页面进行排名。如果您的业务问题涉及页面的量化数据，那么您可通过添加正确的量度来使用此报表解决该问题。
seo-title: 页面
solution: Analytics
title: 页面
topic: 报表
uuid: 6435e262-e734-4c15-af5 b-173799d5 cc43
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 页面

按网站上网页收到的最大流量对页面进行排名。如果您的业务问题涉及页面的量化数据，那么您可通过添加正确的量度来使用此报表解决该问题。

## 分配、过期和特殊值 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

请注意，在“Reports &amp; Analytics”中，页面报表上的量度使用线性分配。例如，收入会分派给购买事件之前查看的所有页面。这会对某些量度造成混淆，您可能希望只出现在一个页面上，例如购物车加货。

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">报表 &amp; <p>Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 量度分配 </td> 
   <td colname="col2"> 线性 </td> 
   <td colname="col3"> 分配特定于各个维度。默认为“最近联系”分配，但“pagename”维度除外。如果您将一个自定义事件应用到“pagename”，则为“精确点击”分配。 </td> 
   <td colname="col4"> <p>相同页面查看上设置的值 </p> </td> 
   <td colname="col5"> <p>相同页面查看上设置的值 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值过期时间 </td> 
   <td colname="col2"> 页面查看 </td> 
   <td colname="col3"> 页面查看 </td> 
   <td colname="col4"> 页面查看 </td> 
   <td colname="col5"> 页面查看 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值限制 </td> 
   <td colname="col2"> <p>每月前 500k 独特值 + 流量中的新值 </p> </td> 
   <td colname="col3"> <p>每月前 500k 独特值 + 流量中的新值 </p> </td> 
   <td colname="col4"> 无 </td> 
   <td colname="col5"> <p>每月前 500k 独特值 + 流量中的新值 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特殊值 </td> 
   <td colname="col2"> <p>（低流量）代表超过前 500k 流量的值，而尚未收到可供报告的足够流量。 </p> </td> 
   <td colname="col3"> <p>（低流量）代表超过前 500k 流量的值，而尚未收到可供报告的足够流量。 </p> </td> 
   <td colname="col4"> 无 </td> 
   <td colname="col5"> <p>（低流量）代表超过前 500k 流量的值，而尚未收到可供报告的足够流量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

在“Reports &amp; Analytics”中，如果您在页面报表中将任何自定义事件作为量度来应用，则会应用线性分配。

这意味着即使事件是通过 s.tl() 调用发送的，该事件仍会获取之前任何 s.t() 调用的线性分配。示例：

| 页面名称 | Page_event | 事件 |
|---|---|---|
| 页面 1 | **s.t()** |  |
| 页面 1 | s.tl() | Event1 |
| 页面 1 | s.tl() | Event1 |
| 页面 1 | s.tl() | Event1 |
| 页面 2 | **s.t()** |  |
| 页面 2 | **s.t()** |  |
| 页面 2 | s.tl() | Event1 |

对于这种情况，我们将在页面报表中获取以下分配：

| 页面 | 页面查看 | Event 1 |
|---|---|---|
| 页面 1 | 1 | 1+1+1+1/3 = 3.33 |
| 页面 2 | 2 | 2/3 = 0.67 |

即使事件是通过 s.tl 调用发送的，在发送的事件（s.t() 调用）之前查看的页面仍将获得部分信用。

## 注释 {#section_47B0F4746D4847AC9E8697127063F4D0}

* 如果页面名称不存在，则使用 URL。
* 如果某个点击没有页面名称、页面 URL 或事件列表（没有商务事件），则该点击将被排除。
* 页面上的划分显示具有持续值的所有页面。

