---
description: 数据连接器的emarsys集成使用Analytics变量跟踪各种emarsys指标。
seo-description: 数据连接器的emarsys集成使用Analytics变量跟踪各种emarsys指标。
seo-title: Analytics 变量
title: Analytics 变量
uuid: 4d5e087c-f495-4aab-9ad1-9b901 d34 a254
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics 变量{#analytics-variables}

数据连接器的emarsys集成使用Analytics变量跟踪各种emarsys指标。

识别Event和eVar与emarsys集成一起使用后，在 [Admin Console中启用它们](https://microsite.omniture.com/t2/help/en_US/reference/index.html?f=conversion_var_admin)。

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
   <td colname="col1"> event(数字) </td> 
   <td colname="col2"> 退回总次数 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>“跳出总弹回”事件可让您查看由于交付问题而未发送给收件人的电子邮件数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event(数字) </td> 
   <td colname="col2"> Clicked </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>单击“单击”事件可查看单击该电子邮件的访客的数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event(数字) </td> 
   <td colname="col2"> 已打开 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>打开的活动可让您查看打开电子邮件的访客的数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event(数字) </td> 
   <td colname="col2"> 已发送 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>发送事件可让您查看发送的电子邮件数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event(数字) </td> 
   <td colname="col2"> 取消订阅 </td> 
   <td colname="col3"> <p>自动从emarsys导入 </p> </td> 
   <td colname="col4"> <p>通过取消订阅活动，您可以查看打开电子邮件的访客数量，然后单击取消订阅链接以选择您的单位以后的电子邮件消息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>通过自动收集方法或JavaScript插件从电子邮件链接的查询参数中收集。 </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar或s. campaign </td> 
   <td colname="col2"> 消息ID </td> 
   <td colname="col3"> <p>通过自动收集方法或JavaScript插件从电子邮件链接的查询参数中收集。 </p> </td> 
   <td colname="col4"> 此值通常存储在营销活动变量中。 </td> 
  </tr> 
 </tbody> 
</table>

