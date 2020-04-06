---
description: Analytics报告API的比较表。 提供支持文档的链接。
title: Analytics 报表 API 比较
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analytics 报表 API 比较

Analytics报告API的比较表。 提供支持文档的链接。

>[!NOTE] 针对延迟，Analytics for Target (A4T) 将整合有关同一点击的 Analytics 和 Target 数据以进行综合报告。由于Analytics和目标调用在不同的时间发生，因此在进行任何处理以从两个解决方案收集数据之前，都会存储点击量。 此过程会 **为所有检查点增加** 7-10分钟的延迟。

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API类型 </th> 
   <th colname="col2" class="entry"> 完全处理 </th> 
   <th colname="col3" class="entry"> 实时 </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>描述</b> </td> 
   <td colname="col2"> 可在所有Analytics界面中使用的经过完全处理的最终数据。 </td> 
   <td colname="col3"> 在收集后数秒内即可获得部分处理的有限指标。 </td> 
   <td colname="col4"> 部分处理的点击数据在收集数秒内可用。 </td> 
   <td colname="col5"> 经过充分处理、最终完成的数据，用于拉动大数据导出。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf"  > 延迟</a> </p> </td> 
   <td colname="col2"> 30-90分钟 </td> 
   <td colname="col3"> *秒-10分钟 </td> 
   <td colname="col4"> 秒-10分钟 </td> 
   <td colname="col5"> 90 分钟 + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理完成</b> </td> 
   <td colname="col2"> 完整 </td> 
   <td colname="col3"> 部分 </td> 
   <td colname="col4"> 部分 </td> 
   <td colname="col5"> 完整 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/zh_CN/reference/"  > 报表接口</a> </td> 
   <td colname="col2"> Reports &amp; Analytics, Report Builder,API </td> 
   <td colname="col3"> Reports &amp; Analytics、Report Builder、API中的实时报告 </td> 
   <td colname="col4"> 仅限API </td> 
   <td colname="col5"> 数据仓库和API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>数据粒度</b> </td> 
   <td colname="col2"> 摘要 </td> 
   <td colname="col3"> 摘要 </td> 
   <td colname="col4"> 点击级别 </td> 
   <td colname="col5"> 摘要 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>访客用户档案处理</b> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 否 </td> 
   <td colname="col5"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>支持细分</b> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 否 </td> 
   <td colname="col5"> 是（但仅限与数据仓库兼容的区段） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> 标准+ </td> 
   <td colname="col3"> 标准+ </td> 
   <td colname="col4"> Premium Complete或Predictive Intelligence </td> 
   <td colname="col5"> 标准+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>文档</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > Web 服务</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > 实时报表</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > 实时流概述</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/zh_CN/reference/data_warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**相关帮助**

* [Adobe/IO](https://www.adobe.io/) —— 将Adobe技术集成到应用程序中所需的技术文档和工具的全面来源。
* [Data Workbench查询API](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

