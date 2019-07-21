---
description: 访客迁移是访客 ID Cookie 从一个域迁移到另一个域的过程。
keywords: Analytics 实施
seo-description: 访客迁移是访客 ID Cookie 从一个域迁移到另一个域的过程。
seo-title: 访客迁移
solution: Analytics
title: 访客迁移
topic: 开发人员和实施
uuid: af31928c-85d7-407f-a583-3c8 f2852 cf3
translation-type: tm+mt
source-git-commit: 85dbc654643f63e30cb20df7e6e9e4cff8660c05

---


# 访客迁移

访客迁移是访客 ID Cookie 从一个域迁移到另一个域的过程。

通过访客迁移可以在更改数据收集域时保留访客识别 Cookie。数据收集域可能由于以下原因发生更改：

* Moving from `2o7.net` to `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/)).

* You are implementing the [Experience Cloud Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) and are moving from a CNAME/first-party data collection domain to `2o7.net` or `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/))

* Moving from `2o7.net` or `omtrdc.net` to a cname/first-party data collection ( [First-Party Cookies)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/).

* 在 CNAME 之间转移（更改域）。

配置完访客迁移后，当用户访问没有访客 ID Cookie 的新域时，服务器会重定向到前一个数据收集主机名，检索任何可用的访客 ID Cookie，并再次重定向到新域。如果前一个主机名上找不到访客 ID，则会生成一个新的 ID。这对每个访客只会出现一次。

## 访客迁移过程 {#section_FF0C5C5CAEF343FFA1892B29311F7160}

下表列出了访客迁移所需的任务：

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>开始：</b> <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="http" scope="external">联系客户关怀</a>，告知您要迁移的域以及希望启用的迁移周期（30、60 或 90 天）。请务必加入非安全和安全域。 </p> </td> 
   <td colname="col3"> <p>使用 <i>exact</i> 语法创建一个列表，包含您希望作为迁移源或迁移目标的域。 </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>迁移主机名在 Adobe Data 收集服务器上配置。客户关怀会告知您何时进行更改，以便您为下一步做好计划。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>在完成配置更改的 6 小时后</b>：更新您的 Analytics JavaScript 代码中的 <code>s.trackingServer</code> 和 <code>s.trackingServerSecure</code> 变量，从而使用新的数据收集服务器。 </p> </td> 
   <td colname="col3"> <p>After you make this change, use a <a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local"> Packet Analyzer</a> to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>更新 Analytics 代码之后立即执行</b>：测试网站，验证是否会重定向到之前的数据收集域。 </p> </td> 
   <td colname="col3"> <p>使用<a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local"> 包分析器</a> 可验证首次访问站点时或清除cookie后，您在200(确定) HTTP状态代码之前看到两个302(重定向) HTTP状态代码。如果这些重定向中有任何一个出现失败，请立即联系客户关怀，确保迁移配置正确。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>整个迁移期间</b>：保持前一个主机名的 DNS 记录的活动状态。 </p> </td> 
   <td colname="col3"> <p>前一个主机名必须通过 DNS 解析，否则 Cookie 迁移无法进行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已弃用的 visitorMigrationKey 和 visitorMigrationServer 变量 {#section_32FCEE2575944D039EA0FEBFB5814259}

As of March 2013, the `visitorMigrationKey`, `visitorMigrationServer`, and `visitorMigrationServerSecure` data collection variables are deprecated and no longer used. 之前在这些变量中包含的数据现存储在 Adobe 服务器上，安全性更高。
