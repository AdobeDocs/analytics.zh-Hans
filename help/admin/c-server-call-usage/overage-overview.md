---
description: 'null'
title: “服务器调用使用情况”概述
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# “服务器调用使用情况”概述

## 为何要监控服务器调用使用情况并发出警报？{#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics Server调用使用将透明度请求发送到浏览器和移动服务器调用使用数据。 它允许您访问：

* 一个服务器调用使用仪表板，它跟踪服务器调用使用情况数据并将其与合同限制进行比较。(**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* A Server Call Usage alert type in the Alert Builder that lets you set up alerts to prevent overages (**[!UICONTROL Analytics > Components >Alerts]**)

服务器调用使用的主要益处包括：

* **了解** 您的服务器调用使用情况和承诺数据，包括与合同服务器调用使用限制相比的移动使用情况。
* **提醒** ，通知您超额使用的风险或发生情况，并准备／应对可能发生超额使用的情况。

Previously, while you could access monthly server call consumption data under  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]** , this data was only updated 6 days after billing had closed for that month. 此外，此数据并不包含移动设备使用量。此功能还将替换>下的 **[!UICONTROL Billing Information]** 当前报 **[!UICONTROL Analytics]** 告 **[!UICONTROL Reports]** 。

## 先决条件 {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **权限：**&#x200B;要访问“服务器调用使用情况”功能板和“警报生成器/管理器”，您必须是 Adobe Analytics 管理员。
* **权限：** 管理员可以授予非管理员访问权限：该权限称为 **[!UICONTROL Server Call Usage]**。 请参阅[“服务器调用使用情况”权限](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369)。

## 重要术语 {#section_CBA348A039F34563B097CD8890AB358D}

以下是关于服务器调用使用的基本术语的简短入门：

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
   <td colname="col2"> <p>服务器调用（也称为“点击”或“图像请求”）是将数据发送到Adobe服务器以进行处理的实例。 最常见的服务器调用类型是页面视图。 在一次页面查看中，访客会查看您网站上的一个页面，同时将生成一个对 Adobe 的服务器调用；在该调用过程中将对信息进行收集和处理，并将其包含在您的报表量度中。 </p> <p>还有其他类型的服务器调用，包括退出链接和文件下载，其中数据会发送到Adobe以进行处理，但不会记录为新页面视图。 即使是“被排除”的页面视图（例如，按您配置的IP地址范围从报表中排除）也是服务器调用，因为Adobe会接收并处理这些页面，但不会显示在报表中。 </p> <p><b>主服务器调用</b>:直接从网站访客浏览器或数据插入API接收的请求。 包括主要点击(页面视图)、主要自定义事件、主要下载事件和主要退出事件。 </p> <p><b>辅助服务器调用</b>:由多套件标记创建或由VISTA规则复制／移动的主服务器调用的副本。 如果VISTA规则将次服务器调用移动（未复制）到其他报表包，则从主服务器调用中扣除累积的次服务器调用。 </p> <p><b>移动主服务器调用 </b> </p> <p>直接从其中一个 Mobile SDK 收到的请求。包括 trackAction、trackState、trackApp 崩溃次数、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrease。</p> <p><b>移动辅助服务器调用</b> </p> <p>由多报表包标记创建或由 VISTA 规则复制/移动的主服务器调用的副本。如果VISTA规则将次服务器调用移动（未复制）到其他报表包，则从主服务器调用中扣除累积的次服务器调用。 </p> <p>注意：如果按合同规定贵公司仅有权使用移动设备服务器调用（主调用或次级调用），则会按特定于移动设备的承诺使用量来计算特定于 Web 及移动设备的调用使用量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>开单公司（开单ID） </p> </td> 
   <td colname="col2"> <p>为服务器调用计费的法律实体。 例如，adobe.com。 每个付费公司都有一个付费ID，用于唯一标识付费客户。 一个付费ID可以绑定到多个Experience Cloud组织；组织与开单ID之间并不总是存在1:1关系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>登录公司 </p> </td> 
   <td colname="col2"> <p>一个账单公司可以拥有<a href="https://helpx.adobe.com/cn/analytics/kb/multiple-login-companies.html">多个登录公司</a>。登录公司是您的组织使用的报表包的集合。 某些组织具有多个登录公司，这些登录适用于组织的不同部分。 对于处理不同业务单位的大型组织而言，这尤其有用，因为许多报表包不适用于公司中的其他部门。 </p> <p>通常，这些是公司的地区分支。 此示例显示登录公司及其关联的报表包： </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide:RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us:RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in:RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de:RS4 </li> 
    </ul> <p>注意：一个账单公司所拥有的<u>所有</u>报表包的服务器调用使用情况数据对具有相应<a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">权限</a>的所有用户都可见。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud组织 </p> </td> 
   <td colname="col2"> <p> 组织是一个实体，它允许管理员配置群组和用户，并控制 Experience Cloud 中的单点登录。组织的作用类似于一个衔接所有 Experience Cloud 产品和解决方案的登录公司。 </p> <p>大多数情况下，组织是您的公司名称。 但是，公司可以有许多组织。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>服务器调用承诺 </p> </td> 
   <td colname="col2"> <p>当您的公司与Adobe签订合同时，Adobe销售团队会向您、客户确认合同期内预计会发生的服务器调用类型（主要、次要、移动主要、移动辅助）和大致数量。 这是您的服务器调用总承诺。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用期 </p> </td> 
   <td colname="col2"> <p>为了监控服务器调用使用情况，将此总服务器调用承诺细分为较短的使用期（如3个月），以便于进行年度比较。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合同期 </p> </td> 
   <td colname="col2"> <p>合同期可以延长多年。 假设您的公司在3年的合同期内有600万次服务器呼叫承诺。 出于监测服务器调用使用情况的目的，可以将 3 年的合同期细分为较短的使用时段，以便于进行年度环比分析。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## “服务器调用使用情况”权限{#section_FCC58EB635954A32990D4E67B52B4369}

“服务器调用使用情况”权限会自动授予Analytics管理员。 它允许用户视图仪表板并创建服务器调用警报。 管理员可以选择向非管理员授予此权限。

>[!NOTE] 贵公司可以选择哪些登录公司有权访问“服务器调用使用情况”。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 权限名称 </th> 
   <th colname="col3" class="entry"> 如果您登录到Adobe Analytics（旧版登录），请授予权限 </th> 
   <th colname="col4" class="entry"> 如果您登录到Adobe Experience Cloud，请授予权限 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>服务器调用使用情况 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">通过sc.omniture.com登录到Analytics。 </li> 
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

