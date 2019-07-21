---
description: Analytics 报表 API 的比较表。提供了支持文档的链接。
seo-description: Analytics 报表 API 的比较表。提供了支持文档的链接。
seo-title: Analytics 报表 API 比较
solution: Analytics
title: Analytics 报表 API 比较
uuid: fa533a8e-33c0-42f4-a294-cabee0258 c f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Analytics 报表 API 比较

Analytics 报表 API 的比较表。提供了支持文档的链接。

>[!NOTE]
>
>对于滞后时间，Analytics for Target(A4T)将Analytics和Target数据与集成报告相结合。由于 Analytics 和 Target 调用在不同的时间发生，因此在进行任何处理以从这两个解决方案收集数据之前，将会存储点击。此过程在所有检查点处增加了&#x200B;**额外 7-10 分钟**&#x200B;的延迟。

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
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf" format="https" scope="external"> 延迟</a> </p> </td> 
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
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/" format="https" scope="external"> 报表接口</a> </td> 
   <td colname="col2"> Reports &amp; Analytics、Report Builder、API </td> 
   <td colname="col3"> Reports &amp; Analytics 中的实时报表、Report Builder、API </td> 
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
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> 标准+ </td> 
   <td colname="col3"> 标准+ </td> 
   <td colname="col4"> Premium Complete 或 Predictive Intelligence </td> 
   <td colname="col5"> 标准+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>文档</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B" format="https" scope="external"> Web 服务</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time" format="https" scope="external"> 实时报表</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B" format="https" scope="external"> 实时流概述</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html" format="https" scope="external"> Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**相关帮助**

* [Adobe/IO](https://www.adobe.io/) - 将 Adobe 技术集成到应用程序所需的技术文档和工具的综合性源。
* [Data Workbench 查询 API](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

