---
description: emarsys 的 Data Connectors 集成使用 Analytics 变量来跟踪不同的 emarsys 量度。
title: Analytics 变量
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics 变量{#analytics-variables}

emarsys 的 Data Connectors 集成使用 Analytics 变量来跟踪不同的 emarsys 量度。

在确定要与 emarsys 集成一起使用的事件和 eVar 后，在 [Admin Console](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/c-admin-tools.html) 中启用它们。

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
   <td colname="col1"> 事件（数字） </td> 
   <td colname="col2"> 退回总计 </td> 
   <td colname="col3"> <p>自动从 emarsys 导入 </p> </td> 
   <td colname="col4"> <p>“退回总计”事件让您能够查看由于传输问题而未发送给收件人的电子邮件数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件（数字） </td> 
   <td colname="col2"> 已点击 </td> 
   <td colname="col3"> <p>自动从 emarsys 导入 </p> </td> 
   <td colname="col4"> <p>“已点击”事件让您能够查看点击了电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件（数字） </td> 
   <td colname="col2"> 已打开 </td> 
   <td colname="col3"> <p>自动从 emarsys 导入 </p> </td> 
   <td colname="col4"> <p>“已打开”事件让您能够查看打开了电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件（数字） </td> 
   <td colname="col2"> 已发送 </td> 
   <td colname="col3"> <p>自动从 emarsys 导入 </p> </td> 
   <td colname="col4"> <p>“已发送”事件让您能够查看已发送的电子邮件数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件（数字） </td> 
   <td colname="col2"> 已取消订阅 </td> 
   <td colname="col3"> <p>自动从 emarsys 导入 </p> </td> 
   <td colname="col4"> <p>“已取消订阅”事件让您能够查看以下访客的数量：打开了电子邮件，但随后单击“取消订阅”链接以选择退出接收贵组织今后的电子邮件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 收件人 ID </td> 
   <td colname="col3"> <p>通过自动收集方法或 JavaScript 插件，从电子邮件链接中的查询参数收集。 </p> </td> 
   <td colname="col4"> 收件人 ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar 或 s.campaign </td> 
   <td colname="col2"> 消息 ID </td> 
   <td colname="col3"> <p>通过自动收集方法或 JavaScript 插件，从电子邮件链接中的查询参数收集。 </p> </td> 
   <td colname="col4"> 此值通常存储在促销活动变量中。 </td> 
  </tr> 
 </tbody> 
</table>

