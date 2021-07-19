---
description: Analytics 报表 API 的比较表。提供了支持文档的链接。
title: Analytics 报表 API 比较
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
feature: API
role: Developer
exl-id: 924f591d-b6ed-4dae-aa69-72d72217e7bd
source-git-commit: 3867573780a791ec4cf2b2ceda33707d972f3f5c
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

---

# Analytics 报表 API 比较

Analytics 报表 API 的比较表。提供了支持文档的链接。

>[!NOTE]
>
>针对延迟，Analytics for Target (A4T) 将整合有关同一点击的 Analytics 和 Target 数据以进行综合报告。由于 Analytics 和 Target 调用在不同的时间发生，因此在进行任何处理以从这两个解决方案收集数据之前，将会存储点击。此过程在所有检查点处增加了&#x200B;**额外 7-10 分钟**&#x200B;的延迟。

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API 类型 </th> 
   <th colname="col2" class="entry"> 完全处理 </th> 
   <th colname="col3" class="entry"> 实时 </th> 
   <th colname="col4" class="entry"> 实时流 </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>描述</b> </td> 
   <td colname="col2"> 所有 Analytics 界面中可用的完全处理的完成数据。 </td> 
   <td colname="col3"> 收集时间段（秒）内可用的部分处理的有限量度。 </td> 
   <td colname="col4"> 收集时间段（秒）内可用的部分处理的点击数据。 </td> 
   <td colname="col5"> 用于提取大型数据导出的完全处理的完成数据。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://experienceleague.adobe.com/docs/analytics/technotes/latency.html?lang=zh-Hans"  > 延迟</a> </p> </td> 
   <td colname="col2"> 30-90 分钟 </td> 
   <td colname="col3"> * 数秒 - 10 分钟 </td> 
   <td colname="col4"> 数秒 - 10 分钟 </td> 
   <td colname="col5"> 90 分钟 + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理完成</b> </td> 
   <td colname="col2"> 完全 </td> 
   <td colname="col3"> 部分 </td> 
   <td colname="col4"> 部分 </td> 
   <td colname="col5"> 完全 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://experienceleague.adobe.com/docs/analytics/landing/home.html?lang=zh-Hans"  > 报表界面</a> </td> 
   <td colname="col2"> Analysis Workspace、Reports &amp; Analytics、Report Builder、API </td> 
   <td colname="col3"> Reports &amp; Analytics、Report Builder、1.4 API 中的实时报表 </td> 
   <td colname="col4"> 仅限 API </td> 
   <td colname="col5"> Data Warehouse 与 API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>数据粒度</b> </td> 
   <td colname="col2"> 汇总 </td> 
   <td colname="col3"> 汇总 </td> 
   <td colname="col4"> 点击级别 </td> 
   <td colname="col5"> 汇总 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>访客资料处理</b> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 否 </td> 
   <td colname="col5"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>支持区段</b> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 否 </td> 
   <td colname="col5"> 是（但仅限 Data Warehouse 兼容的区段） </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <b>文档</b> </td> 
   <td colname="col2"> <p> <a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html"  > Analytics API</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis"  > 实时报表</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md"  > 实时流概述</a> </p> </td> 
   <td colname="col5"> <p><a href="https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=zh-Hans"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**相关帮助**

* [Adobe/IO](https://www.adobe.io/) - 将 Adobe 技术集成到应用程序所需的技术文档和工具的综合性源。
