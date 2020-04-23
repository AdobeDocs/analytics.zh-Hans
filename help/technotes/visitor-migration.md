---
description: 访客迁移是访客 ID Cookie 从一个域迁移到另一个域的过程。
keywords: Analytics Implementation
title: 访客迁移
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# 访客迁移

访客迁移是访客 ID Cookie 从一个域迁移到另一个域的过程。

访客迁移允许您在更改数据收集域时保留访客标识Cookie。 数据收集域可能因以下原因而发生更改：

* 从 `2o7.net` 转移到 `omtrdc.net`（[区域数据收集](https://marketing.adobe.com/resources/help/zh_CN/whitepapers/rdc/)）。

* 您将要实施 [Experience Cloud 访客 ID 服务](https://marketing.adobe.com/resources/help/zh_CN/mcvid/)并从 CNAME/第一方数据收集域转移到 `2o7.net` 或 `omtrdc.net`（[区域数据收集](https://marketing.adobe.com/resources/help/zh_CN/whitepapers/rdc/)）。

* 从 `2o7.net` 或 `omtrdc.net` 转移到 CNAME/第一方数据收集（[第一方 Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)）。

* 从一个CNAME移动到另一个CNAME（更改域）。

配置访客迁移后，当用户访问新域时，如果没有访客ID cookie，则服务器将重定向到以前的数据收集主机名，检索任何可用的访客ID cookie，然后重定向回新域。 如果在上一个主机名上找不到访客ID，则会生成新ID。 每个访客只发生一次。

## 访客迁移过程 {#section_FF0C5C5CAEF343FFA1892B29311F7160}

下表列表了访客迁移所需的任务:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>开始：</b> <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html"  >联系客户关怀</a>，告知您要迁移的域以及希望启用的迁移周期（30、60 或 90 天）。确保包括非安全和安全域。 </p> </td> 
   <td colname="col3"> <p>为要迁移到的 <i>域</i> ，使用精确语法创建列表。 </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>迁移主机名在Adobe数据收集服务器上配置。 客户关怀团队将在更改后通知您，以便您为下一步做好规划。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>在完成配置更改的 6 小时后</b>：更新您的 Analytics JavaScript 代码中的 <code> s.trackingServer</code> 和 <code> s.trackingServerSecure</code> 变量，从而使用新的数据收集服务器。 </p> </td> 
   <td colname="col3"> <p>After you make this change, use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>更新Analytics代码后立即更新</b>:测试站点以验证是否正在重定向到以前的数据收集域。 </p> </td> 
   <td colname="col3"> <p>Use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that when you access your site for the first time, or after clearing cookies, you see two 302 (redirect) HTTP status codes before the 200 (OK) HTTP status code. 如果这些重定向中的任何重定向失败，请立即联系客户服务中心，以确保正确配置迁移。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>在整个迁移期间</b>:保持上一个主机名的DNS记录处于活动状态。 </p> </td> 
   <td colname="col3"> <p>以前的主机名必须通过DNS解析，否则将不会进行Cookie迁移。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已弃用的visitorMigrationKey和visitorMigrationServer变量 {#section_32FCEE2575944D039EA0FEBFB5814259}

自 2013 年 3 月起，`visitorMigrationKey`、`visitorMigrationServer` 和 `visitorMigrationServerSecure` 数据收集变量将被放弃，不会再使用。之前在这些变量中包含的数据现存储在 Adobe 服务器上，安全性更高。
