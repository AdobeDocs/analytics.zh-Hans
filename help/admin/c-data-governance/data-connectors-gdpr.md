---
description: 此页面列出了 Data Connectors（以前称为 Genesis）中的所有合作伙伴变量，这些变量可能包含数据主体的直接可识别数据或间接可识别数据。
title: 数据隐私和 Data Connectors (Genesis)
feature: Privacy
exl-id: 7f75c1b9-5553-414a-a43a-7b44ecb1c564
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: ht
source-wordcount: '87'
ht-degree: 100%

---

# 数据隐私和 Data Connectors (Genesis)

>[!NOTE]
>
>**自 2021 年 8 月 19 日起**，Adobe 已中断数据连接器集成。生命周期终止是任何技术产品生命周期的一部分，Adobe 旨在尽可能地让客户和合作伙伴实现无缝过渡。这些集成中的许多资源可通过 Adobe Exchange 获得，并可以继续加以利用。

<!--This page lists all the Partner variables in the Data Connectors (previously known as Genesis) that could potentially contain data subjects' directly identifiable data or indirectly identifiable data.

This information lets you identify any directly identifiable data or indirectly identifiable data imported via our connectors, when they receive a Data Privacy request.

If you are using an integration of any of the below connectors, you can simply check which partner variables/classifications in your integration may potentially contain directly identifiable data or indirectly identifiable data.

>[!NOTE]
>
>This information is provided to help you identify variables that must be [labeled](/help/admin/c-data-governance/gdpr-setup-reportsuite.md), but it is your responsibility as the data controller to apply the appropriate labels or perform other actions for [Data Privacy readiness](/help/admin/c-data-governance/an-gdpr-overview.md) (updating classifications, etc.).

<table id="table_4DE59253898D46E282EF5F9CB0ED34B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Connector Name </th> 
   <th colname="col2" class="entry"> Variables </th> 
   <th colname="col4" class="entry"> Type </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Alset</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>appFigures</b> </p> </td> 
   <td colname="col2"> <p>App Store Object ID -&gt; App Store User </p> <p>App Store Object ID -&gt; Review Comment </p> <p>App Store Object ID -&gt; Review Title </p> </td> 
   <td colname="col4"> <p>Classifications </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Aprimo Enterprise Marketing Management</b> </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>CheetahMail</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>ContactLab 2.0</b> </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Datran Media</b> </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Delivra</b> </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p><b>Dialog Tech</b> </p> </td> 
   <td colname="col2"> <p>Dialog Tech Caller </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Dialog Tech Caller -&gt; City </p> <p>Dialog Tech Caller -&gt; First Name </p> <p>Dialog Tech Caller -&gt; Last Name </p> <p>Dialog Tech Caller -&gt; State </p> <p>Dialog Tech Caller -&gt; Street Address </p> <p>Dialog Tech Caller -&gt; Zip Code </p> </td> 
   <td colname="col4"> <p>Classifications </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>DREAMmail 2.0</b> </p> </td> 
   <td colname="col2"> <p>Email eVar </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Dynamic Signal</b> </p> </td> 
   <td colname="col2"> <p>Tracking Code -&gt; Source ID </p> <p>Tracking Code -&gt; Source Name </p> <p>Tracking Code -&gt; User ID </p> <p>Tracking Code -&gt; User Name </p> </td> 
   <td colname="col4"> <p>Classifications </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>eDialog Precision Central</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Emarsys Xpress</b> </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p><b>Emailvision Campaign Commander</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Message ID -&gt; Mailing List Name </p> <p>Message ID -&gt; Manager ID </p> <p>Message ID -&gt; Manager Name </p> </td> 
   <td colname="col4"> <p>Classifications </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Epsilon Harmony</b> </p> </td> 
   <td colname="col2"> <p>Email Address </p> <p>Customer Key </p> </td> 
   <td colname="col4"> <p>eVar </p> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exact Target</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p><b>ForeSee (v2.0)</b> </p> </td> 
   <td colname="col2"> <p>Foresee Respondent ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Foresee Respondent ID -&gt; variable name 1 </p> <p>... </p> <p>Foresee Respondent ID -&gt; variable name n </p> </td> 
   <td colname="col4"> <p>Classifications </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Foresee Feedback</b> </p> </td> 
   <td colname="col2"> <p>ForeSee Response List -&gt; Response </p> <p>ForeSee Response List -&gt; Survey &gt; Question &gt; Response </p> </td> 
   <td colname="col4"> <p>Classifications </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Listrak</b> </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Lyris HQ</b> </p> </td> 
   <td colname="col2"> <p>Email Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Neolane - Enterprise Marketing Platform</b> </p> </td> 
   <td colname="col2"> <p>Broadlog ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>optivo broadmail</b> </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Responsys</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Responsys 2.0</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> <p>Customer ID </p> </td> 
   <td colname="col4"> <p>eVar </p> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p><b>Selligent</b> </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Recipient ID -&gt; RecipientField1 </p> <p>Recipient ID -&gt; RecipientField2 </p> <p>Recipient ID -&gt; RecipientField3 </p> <p>Recipient ID -&gt; RecipientField4 </p> <p>Recipient ID -&gt; RecipientField5 </p> </td> 
   <td colname="col4"> <p>Classifications </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Silverpop Engage</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Silverpop Engage (v2.0)</b> </p> </td> 
   <td colname="col2"> <p>Silverpop ID </p> <p>Email Address </p> </td> 
   <td colname="col4"> <p>eVar </p> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Synergy!360</b> </p> </td> 
   <td colname="col2"> <p>Customer ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>ThinData EMS</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>WhatCounts Email</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Yesmail Enterprise</b> </p> </td> 
   <td colname="col2"> <p>Visitor ID </p> </td> 
   <td colname="col4"> <p>eVar </p> </td> 
  </tr> 
 </tbody> 
</table>-->
