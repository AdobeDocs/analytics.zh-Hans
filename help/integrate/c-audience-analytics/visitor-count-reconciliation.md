---
description: Adobe Analytics 和 Adobe Audience Manager 中有一些访客量度具有相似的定义，但由于各种原因并不是完全一致。
title: 访客计数差异
uuid: c3bbb887-bd02-4c1c-9a2b-64811c0ef56a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 访客计数差异

Adobe Analytics 和 Adobe Audience Manager 中有一些访客量度具有相似的定义，但由于各种原因并不是完全一致。

访客量度包括：

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> 量度 </th> 
   <th colname="col3" class="entry"> 定义 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html"  > AAM：总区段人口</a> </p> </td> 
   <td colname="col3"> <p>在回顾期间作为区段成员的设备 (Experience Cloud ID) 计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html"  > AAM：实时区段人口</a> </p> </td> 
   <td colname="col3"> <p>在回顾期间作为区段成员或访问过您的属性的设备 (Experience Cloud ID) 计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：独特访客 </p> </td> 
   <td colname="col3"> <p>显示在报告窗口期间访问过您的属性的独特访客数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：具有 Experience Cloud ID 的访客 </p> </td> 
   <td colname="col3"> <p>显示在报告窗口期间访问过您的属性并具有 Experience Cloud ID 的独特访客数量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

AAM 实时区段人口和 Audience Analytics 报表内使用的具有 Experience Cloud ID 的 Analytics 访客将最为相近。但是对于近期而言，由于某些因素，它们之间可能会稍有差异。参与因子包括：

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 因子 </th> 
   <th colname="col2" class="entry"> AAM：实时区段人口 </th> 
   <th colname="col3" class="entry"> Analytics：具有 Experience Cloud ID 的访客 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>时区 </p> </td> 
   <td colname="col2"> <p>UTC（协调世界时） </p> </td> 
   <td colname="col3"> <p>针对每个报表包指定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义过滤器 </p> </td> 
   <td colname="col2"> <p>否 </p> </td> 
   <td colname="col3"> <p>是，例如 IP 过滤器、机器人过滤器 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>150 个区段限制 </p> </td> 
   <td colname="col2"> <p>否 </p> </td> 
   <td colname="col3"> <p>是 - Analytics 计数可能受 150 个区段集成限制影响而产生最多 5% 的偏差。如果发生截断，“已达到受众限制”将显示在“受众名称”维中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Understanding Segments in Analytics and Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) for additional explanation on the nuances between Analytics and Audience Manager data and segmentation.
