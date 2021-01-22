---
description: Adobe Analytics“服务器调用使用情况”功能概述。
title: “服务器调用使用情况”概述
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: ht
source-git-commit: b3ea538d0d6e6ebbbbd17871aacaed7527cf3976
workflow-type: ht
source-wordcount: '1045'
ht-degree: 100%

---


# “服务器调用使用情况”概述

## 为何要监控服务器调用使用情况并发出警报？{#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics“服务器调用使用情况”功能可根据您的请求为您提供透明的浏览器及移动设备服务器调用使用情况数据。此功能允许您访问以下项：

* “服务器调用使用情况”功能板，可跟踪服务器调用使用情况数据，并将其与合同中的使用限制进行比较。（**[!UICONTROL Analytics > 管理员 > 服务器调用使用情况]**）
* 警报生成器中的“服务器调用使用情况”警报类型，您可以设置警报以防止调用超量（**[!UICONTROL Analytics > 组件 > 警报]**）

“服务器调用使用情况”功能主要具有以下优点：

* **数据可见性**：为您提供服务器调用使用情况和承诺数据，包含与合同所规定服务器调用使用限制相对的移动设备使用量。
* **警报**：可在调用使用量面临超量风险或已超量的情况下向您发送通知，从而让您针对可能的调用超量费用做好准备/采取措施。

之前，您可以在 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 账单]**&#x200B;下方访问每月的服务器调用使用情况数据，但是此数据仅在该月账单结算 6 天后才会更新。此外，此数据并不包含移动设备使用量。此功能还将替代 **[!UICONTROL Analytics]** > **[!UICONTROL 报表]**&#x200B;下方的当前&#x200B;**[!UICONTROL 账单信息]**&#x200B;报表。

## 先决条件 {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **权限：**&#x200B;要访问“服务器调用使用情况”功能板和“警报生成器/管理器”，您必须是 Adobe Analytics 管理员。
* **权限：**&#x200B;管理员能够向非管理员用户授予访问权限：此权限称作&#x200B;**[!UICONTROL 服务器调用使用情况]**。请参阅[“服务器调用使用情况”权限](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369)。

## 重要术语 {#section_CBA348A039F34563B097CD8890AB358D}

下面是对“服务器调用使用情况”重要术语的概要介绍：

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 术语 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>服务器调用 </p> </td> 
   <td colname="col2"> <p>服务器调用又称为“点击”或“图像请求”，它是一种将数据发送到 Adobe 服务器进行处理的实例。最常见的服务器调用类型是页面查看。在一次页面查看中，访客会查看您网站上的一个页面，同时将生成一个对 Adobe 的服务器调用；在该调用过程中将对信息进行收集和处理，并将其包含在您的报表量度中。 </p> <p>其他类型的服务器调用包括退出链接和文件下载，在这些服务器调用中，数据会被发送到 Adobe 进行处理，但不会被记录为新的页面查看。甚至“被排除的”页面查看（例如，按您配置的 IP 地址范围从报表中排除的页面查看）也属于服务器调用，因为 Adobe 将会接收并处理这些页面查看，但不会在您的报表中显示它们。 </p> <p><b>主服务器调用</b>：直接从网站访客浏览器或数据插入 API 接收到的请求。包括主要点击（页面查看次数）、主要自定义事件、主要下载事件和主要退出事件。 </p> <p><b>次级服务器调用</b>：由多报表包标记创建或由 VISTA 规则复制/移动的主服务器调用的副本。如果次级服务器调用由 VISTA 规则移动（不是复制）到了另一个报表包，则会从主服务器调用数中减去次级服务器调用的累计调用数。 </p> <p><b>移动设备主服务器调用</b> </p> <p>直接从其中一个 Mobile SDK 收到的请求。包括 trackAction、trackState、trackApp 崩溃次数、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrease。</p> <p><b>移动设备次级服务器调用</b> </p> <p>由多报表包标记创建或由 VISTA 规则复制/移动的主服务器调用的副本。如果次级服务器调用由 VISTA 规则移动（不是复制）到了另一个报表包，则会从主服务器调用数中减去次级服务器调用的累计调用数。 </p> <p>注意：如果按合同规定贵公司仅有权使用移动设备服务器调用（主调用或次级调用），则会按特定于移动设备的承诺使用量来计算特定于 Web 及移动设备的调用使用量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>账单公司（账单 ID） </p> </td> 
   <td colname="col2"> <p>承担服务器调用费用的法律实体。例如，adobe.com。每个账单公司都有一个可用于唯一标识账单客户的账单 ID。账单 ID 可同时与多个 Experience Cloud 组织绑定；组织和账单 ID 之间并不总是一一对应的关系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>登录公司 </p> </td> 
   <td colname="col2"> <p>一个账单公司可以拥有<a href="https://helpx.adobe.com/cn/analytics/kb/multiple-login-companies.html">多个登录公司</a>。登录公司是由您的组织使用的报表包集合。某些组织具有多个适用于该组织不同部分的登录公司。这特别适用于以下情况：大型组织具有很多不同的业务单位，并且其中的很多报表包并不适用于公司中的其他人员。 </p> <p>通常情况下，登录公司是一家公司在不同地区的子公司。以下示例展示了多个登录公司及其相关联的报表包： </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide：RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us：RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in：RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de：RS4 </li> 
    </ul> <p>注意：一个账单公司所拥有的<u>所有</u>报表包的服务器调用使用情况数据对具有相应<a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">权限</a>的所有用户都可见。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud 组织 </p> </td> 
   <td colname="col2"> <p>组织是一个实体，它允许管理员配置群组和用户，并控制 Experience Cloud 中的单点登录。组织的作用类似于一个衔接所有 Experience Cloud 产品和解决方案的登录公司。 </p> <p>大多数情况下，组织是您的公司名称。但是，公司可以具有多个组织。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>服务器调用使用承诺 </p> </td> 
   <td colname="col2"> <p>贵公司与 Adobe 签订合同后，Adobe 销售团队会与您确认客户、调用类型（主调用、次级调用、移动设备主调用、移动设备次级调用）以及您在合同期限内预计发起的服务器调用次数的近似值。这些便是服务器调用使用承诺的全部内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用时段 </p> </td> 
   <td colname="col2"> <p>出于监测服务器调用使用情况的目的，已将承诺的服务器调用使用总量分成了多个较短的使用时段（如 3 个月），以便于进行年度环比分析。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合同期限 </p> </td> 
   <td colname="col2"> <p>合同期限可以长达多年。假如贵公司承诺在 3 年合同期内实施 6 百万次服务器调用。出于监测服务器调用使用情况的目的，可以将 3 年的合同期细分为较短的使用时段，以便于进行年度环比分析。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## “服务器调用使用情况”权限{#section_FCC58EB635954A32990D4E67B52B4369}

“服务器调用使用情况”权限会自动授予 Analytics 管理员。此权限允许用户访问该功能板和创建服务器调用警报。管理员可以选择向非管理员用户授予此权限。

>[!NOTE]
>
>贵公司可以选择哪些登录公司有权访问“服务器调用使用情况”。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 权限名称 </th> 
   <th colname="col3" class="entry"> 登录到 Adobe Analytics（旧版登录）后授予权限 </th> 
   <th colname="col4" class="entry"> 登录到 Adobe Experience Cloud 后授予权限 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>服务器调用使用情况 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">通过 sc.omniture.com 登录到 Analytics。 </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">导航到<span class="ignoretag"><span class="uicontrol">管理员</span> &gt; <span class="uicontrol">用户管理</span> &gt; <span class="uicontrol">群组</span> &gt; <span class="uicontrol">编辑所有报表访问</span> &gt; <span class="uicontrol">Analytics 工具</span> &gt; <span class="uicontrol">自定义</span> &gt; <span class="uicontrol">服务器调用使用情况 </span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">登录到 login.experiencecloud.adobe.com。</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">单击 <span class="uicontrol">Analytics</span>。 </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">导航到<span class="ignoretag"><span class="uicontrol">产品</span> &gt; <span class="uicontrol">产品配置文件</span> &gt; <span class="uicontrol">权限</span> &gt; <span class="uicontrol">Analytics 工具</span> &gt; <span class="uicontrol">服务器调用使用情况 </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

