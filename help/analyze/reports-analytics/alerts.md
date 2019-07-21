---
description: 'null'
seo-description: 'null'
seo-title: 警报
solution: Analytics
subtopic: 警报
title: 警报
topic: Reports & Analytics
uuid: e1333a9b-eba0-45b7-b7 e6-46e06190 db64
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 警报

## 警报 {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

作为Adobe Analytics的全新警报系统，智能提醒可让您创建和管理警报，并配以警报预览和规则贡献。您可以

* 构建基于异常的警报（90%、95% 或 99% 阈值；% 更改；以上/以下）。
* 预览警报触发的频率。
* 通过含链接的电子邮件或短信将警报发送到自动生成的 Analysis Workspace 项目。
* 创建可在一个警报中捕获了多个量度的“堆栈式”警报。

You can access this new Alerts system from **[!UICONTROL More]** &gt; **[!UICONTROL Alerts]** in any report in Reports &amp; Analytics.

有关更多信息，请转到 Analysis Workspace 文档中的[智能警报](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html)。

## 添加警报 {#task_51187E8BF19544DDA9EF2057E6F11D35}

描述如何在 Adobe Analytics 中添加警报的步骤。

<!-- 

t_add_an_alert.xml

 -->

Navigate to the new Alert Builder in the **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** menu. 但是，您仍然可以从 Reports &amp; Analytics 的报表内访问它：

1. 在 Reports &amp; Analytics 中，打开要在其中设置警报的报表。
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.
1. 这会将您引导至[新的警报生成器](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-builder.html)。

## 查看或编辑现有警报 {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

任务上下文

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]**. 这会将您引导至新的[警报管理器](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-manager.html)。

## 旧警报迁移 {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

现有 Analytics 警报的几项功能将不会包含在 2016 年秋作为 Analysis Workspace 一部分发行的新警报管理器中。下表列出了弃用的警报功能和某些将以其他形式迁移到新警报管理器的警报功能。

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 旧警报功能 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 弃用或迁移？ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>合计（所有项目） </p> </td> 
   <td colname="col2"> <p>对某个维度报表的所有项目创建警报。 </p> </td> 
   <td colname="col3"> <p>在某些情况下，无论您是对某个维度报表的所有项目创建警报，还是只对聚合量度本身设置警报（不适用于维度），都会发生同样的结果。比如说，您可以在“收入”量度中创建一个每月“所有项目”警报。而您在运行“收入”报表并在其中设置每月警报时，会得到同样的结果。 </p> <p>在这种情况下，旧的“合计（所有项目）”警报将不再可用，并将迁移到后面更简单的版本。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>排名最前的 1000 个项目 </p> <p> </p> </td> 
   <td colname="col2"> <p>为报表中排名最前的 1000 个项目创建警报。 </p> </td> 
   <td colname="col3"> <p>在新的警报管理器中不再可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>基于时间的独特访客警报（每日、每周、每月等独特访客） </p> <p> </p> </td> 
   <td colname="col2"> <p>为每小时、每日、每周和每月独特访客报表创建警报。 </p> </td> 
   <td colname="col3"> <p>在新的警报管理器中，某些基于时间的独特访客警报不再受支持。例如，如果您之前能够为每日独特访客设置每周警报，您以后将能够继续在独特访客量度中设置每日、每周等警报。（Analysis Workspace 支持独特访客量度，但不支持每日/每周/每月/等独特访客量度。） </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜索 </p> </td> 
   <td colname="col2"> <p>为应用了搜索的维度报表创建警报。仅适用于“合计”（“所有项目”）或“排名最前的 1000 个项目”。 </p> <p> </p> </td> 
   <td colname="col3"> <p>在新的警报管理器中不再可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 特定于 Reports &amp; Analytics 的报表 </p> </td> 
   <td colname="col2"> <p>为 Reports &amp; Analytics 中存在的几个报表创建警报，并且不与 Analysis Workspace 报表对应，例如 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">路径长度 </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">机器人 </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">时区 </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">顶级域名 </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>在新的警报管理器中不再可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>具有 ASI 插槽的警报作为报表包 </p> </td> 
   <td colname="col2"> <p>不能再<a href="https://marketing.adobe.com/resources/help/en_US/reference/ASI_slots_admin.html" format="https" scope="external">创建或编辑 ASI 插槽</a>，并且在 Analysis Workspace 中不可用。因此，它们不受新警报的支持。 </p> <p> </p> </td> 
   <td colname="col3"> <p>在新的警报管理器中不可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用参与量度的警报 </p> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_participation.html" format="https" scope="external">参与量度</a>在 Reports &amp; Analytics 中可用，但当前在 Analysis Workspace 的新警报系统中不可用。 </p> <p> </p> </td> 
   <td colname="col3"> <p>在新的警报管理器中不可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用于自定义日历报表包的每月警报 </p> </td> 
   <td colname="col2"> <p>这仅会对满足以下条件的客户造成影响：针对具有<a href="https://marketing.adobe.com/resources/help/en_US/arb/custom_calendar.html" format="https" scope="external">自定义月份开始日期</a>（美国零售联合会/NRF 和自定义日历类型）的报表包设置了警报。 </p> <p>它不影响“公历”或“已修改的公历”日历报表包中的警报。以前，这些警报是在公历月份的第一天发送的（例如，1 月 1 日，2 月 1 日等）。这与警报的新“异常检测”功能不相符，因为它在检测异常时会考虑之前月份的数据。以后，我们将增加对计划系统的自定义日历支持，这样警报和计划项目都可以通过计划在自定义日历月的第一天发送，而不只是在公历月的第一天发送。 </p> <p> </p> </td> 
   <td colname="col3"> <p>在新警报管理器中尚不可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自 2015 年 9 月以后没有运行的警报。 </p> </td> 
   <td colname="col2"> <p>警报从 2015 年 9 月起就没有运行可能是出于几个原因，包括： </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">在警报管理器中对该警报单击了“禁用”。 </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">警报在运行时遇到错误，且没有成功完成。 </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> 这些警报将不会迁移到新系统。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已标记为“禁用”的警报 </td> 
   <td colname="col2"> 目前不能在新用户界面中禁用/重新启用警报，不过确有计划添加此功能。 <p> </p> </td> 
   <td colname="col3"> 这些警报将不会迁移到新系统。 </td> 
  </tr> 
 </tbody> 
</table>

