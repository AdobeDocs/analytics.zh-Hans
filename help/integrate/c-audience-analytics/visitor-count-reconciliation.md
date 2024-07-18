---
description: Adobe Analytics 和 Adobe Audience Manager 中有一些访客量度具有相似的定义，但由于各种原因并不是完全一致。
title: 访客计数差异
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 85%

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
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=zh-Hans"  > Adobe Audience Manager：总区段人口</a> </p> </td> 
   <td colname="col3"> <p>在回顾期间作为区段成员的设备 (Experience Cloud ID) 计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=zh-Hans"  > Adobe Audience Manager：实时区段人口</a> </p> </td> 
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

Adobe Audience Manager实时区段人口与Analytics报表中使用的具有Experience CloudID的Audience Analytics访客将最相似。 但是对于近期而言，由于某些因素，它们之间可能会稍有差异。参与因子包括：

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 因素 </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager：实时区段人口 </th> 
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
   <td colname="col3"> <p>是 - Analytics 计数可能受 150 个区段集成限制影响而产生最多 5% 的偏差。如果发生截断，“受众名称”维度中将显示“已达到受众限制”。 </p> </td> 
  </tr> 
 </tbody> 
</table>

请参阅[了解 Analytics 和 Audience Manager 中的区段](/help/integrate/c-audience-analytics/aam-analytics-segments.md)，以获取关于 Analytics 和 Audience Manager 数据与分段之间细微差别的其他解释。
