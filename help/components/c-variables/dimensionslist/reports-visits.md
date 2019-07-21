---
description: 显示指定时间段内整个网站的访问量。
seo-description: 显示指定时间段内整个网站的访问量。
seo-title: 访问次数
solution: Analytics
title: 访问次数
topic: 报表
uuid: ff65bddf-fb65-4cf0-8ae-4ab59 c2 bb0 a7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 访问次数

显示指定时间段内整个网站的访问量。

**报表属性**

* 一次“访问”是指间断时间不超过 30 分钟的连续页面查看或者 12 小时连续活动。
* 访问过期后，新访问将从下一次任意图像请求开始。
* 一位访客通常至少有一次（但可能是多次）访问。
* 一次访问的开始定义为新访客（或现有用户在访问过期后）的第一个图像请求。这可被确认为是登录页面。
* 一次访问的结束定义为访问过期前的最后一个图像请求。这可被确认为是退出页面。

   请参阅 [登录和退出报表](../../../components/c-variables/dimensionslist/reports-entries-exits.md#concept_C4AED2C1D62E43A48ACAA837327FCCF2).
* 小时划分是基于报表包的时区。
* 此报表不包含行项目。您只能以趋势格式查看。
* 可应用“小时”、“日”、“周”、“月”、“季”和“年”粒度。这些粒度设置的可用性取决于报表的日期范围。

请参阅[访问量度](../../../components/c-variables/c-metrics/metrics-visit.md#concept_9DA4D9EF8B964755BAC57378AD37911E)以了解有关 Experience Cloud 如何处理此量度的详细信息。

**产品特定报表信息**

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 产品 </th> 
   <th colname="col2" class="entry"> 导航 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 网站量度</span> &gt; <span class="uicontrol">访问</span> </p> <p>您可以在选定页面上运行<span class="wintitle">访问报表</span>。跨午夜的访问同时被计入访问开始和结束的当天。但是，给定日期范围内的合计将会删除重复的计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 报表</span> &gt; <span class="uicontrol">网站量度</span> &gt; <span class="uicontrol">访问</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> 您可按几乎所有其他报表和变量划分此报表中的每个项目，因此可按任何粒度显示划分结果。 </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">跨午夜的访问同时被计入访问开始和结束的当天。但是，在给定日期范围内的合计将会删除重复的计数。 </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">您可以在此报表中使用所有转化和流量量度，以及对所有转化量度进行不同的分配。 </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">此报表可使用多个非常高级的区段。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

