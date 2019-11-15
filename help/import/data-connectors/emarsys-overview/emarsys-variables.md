---
description: emarsys的Data Connectors集成使用Analytics变量跟踪各种emarsys指标。
title: Analytics 变量
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics 变量{#analytics-variables}

emarsys的Data Connectors集成使用Analytics变量跟踪各种emarsys指标。

在确定要与emarsys集成一起使用的事件和eVar后，在 [Admin Console中启用它们](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/c-admin-tools.html)。

**必需变量**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量类型 </th> 
   <th colname="col2" class="entry"> 名称 </th> 
   <th colname="col3" class="entry"> 填充方法 </th> 
   <th colname="col4" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> event（数字） </td> 
   <td colname="col2"> 总弹回次数 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>通过“弹回总数”事件，您可以查看由于传送问题而未发送给收件人的电子邮件数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数字） </td> 
   <td colname="col2"> 已单击 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>通过“已点击”事件，您可以查看点击电子邮件的访客数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数字） </td> 
   <td colname="col2"> 已打开 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>通过“已打开”活动，您可以查看打开电子邮件的访客数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数字） </td> 
   <td colname="col2"> 已发送 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>“发送”事件可让您查看已发送的电子邮件数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数字） </td> 
   <td colname="col2"> 取消订阅 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>通过取消订阅活动，您可以查看打开电子邮件但随后单击取消订阅链接以选择退出您组织的将来电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>通过自动收集方法或JavaScript插件从电子邮件链接中的查询参数收集。 </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar 或s.campaign </td> 
   <td colname="col2"> 消息ID </td> 
   <td colname="col3"> <p>通过自动收集方法或JavaScript插件从电子邮件链接中的查询参数收集。 </p> </td> 
   <td colname="col4"> 此值通常存储在系列活动变量中。 </td> 
  </tr> 
 </tbody> 
</table>

