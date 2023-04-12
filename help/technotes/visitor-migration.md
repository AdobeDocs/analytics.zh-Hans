---
description: 访客迁移是访客 ID Cookie 从一个域迁移到另一个域的过程。
keywords: Analytics 实施
title: 访客迁移
topic-fix: Developer and implementation
feature: Analytics Basics
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
source-git-commit: 21bbb59cdc630823cf342ff7dd0142b83f89a314
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 88%

---

# 访客迁移

>[!NOTE]
>
>如果您已经实施Experience Cloud访客ID服务，则宽限期不适用于您，因此不应该启用宽限期。

访客迁移是访客ID Cookie(s_vi)从一个域迁移到另一个域的过程。

通过访客迁移可以在更改数据收集域时保留访客识别 Cookie。数据收集域可能由于以下原因发生更改：

* 从 `2o7.net` 迁移到 `adobedc.net`。

* 您在实施 [Experience Cloud 访客 ID 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans) 并从 CNAME/第一方数据收集域迁移到 `adobedc.net`、`2o7.net` 或 `omtrdc.net`

* 从 cname/第一方数据收集迁移（[第一方 Cookie）](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hans)。

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
   <td colname="col1"> <p> <b>开始：</b> <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html"  >联系客户关怀</a>，告知您要迁移的域以及希望启用的迁移周期（30、60 或 90 天）。确保包含非安全和安全域。 </p> </td> 
   <td colname="col3"> <p>使用 <i>exact</i> 语法创建一个列表，包含您希望作为迁移源或迁移目标的域。 </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>迁移主机名在 Adobe Data 收集服务器上配置。客户关怀会告知您何时进行更改，以便您为下一步做好计划。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>在完成配置更改的 6 小时后</b>：更新您的 Analytics JavaScript 代码中的 <code> s.trackingServer</code> 和 <code> s.trackingServerSecure</code> 变量，从而使用新的数据收集服务器。 </p> </td> 
   <td colname="col3"> <p>进行此更改后，使用 <a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html">Experience Cloud Debugger</a> 验证 Analytics 图像请求传送到了更新后的数据收集服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>更新 Analytics 代码之后立即执行</b>：测试网站，验证是否会重定向到之前的数据收集域。 </p> </td> 
   <td colname="col3"> <p>使用<a href="../implement/validate/packet-monitor.md">数据包监视器</a> 验证在您首次或者清除 Cookie 之后访问网站时，在 200 (OK) HTTP 状态代码之前看到了两个 302（重定向）HTTP 状态代码。如果这些重定向中有任何一个出现失败，请立即联系客户关怀，确保迁移配置正确。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>整个迁移期间</b>：保持前一个主机名的 DNS 记录的活动状态。 </p> </td> 
   <td colname="col3"> <p>前一个主机名必须通过 DNS 解析，否则 Cookie 迁移无法进行。 </p> </td> 
  </tr> 
 </tbody> 
</table>
