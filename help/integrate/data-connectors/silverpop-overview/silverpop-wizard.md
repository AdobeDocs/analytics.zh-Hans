---
description: 数据连接器集成向导将指导您逐步完成数据连接器集成过程。
seo-description: 数据连接器集成向导将指导您逐步完成数据连接器集成过程。
seo-title: Silverpop集成
title: Silverpop集成
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Silverpop Integration{#silverpop-integration}

数据连接器集成向导将指导您逐步完成数据连接器集成过程。

配置集成：

1. 在Adobe Marketing Cloud中，从产品下拉列表中选择“数据连接器™”。
1. Click **[!UICONTROL Add New]** and select **[!UICONTROL By Name]** in the **[!UICONTROL Show]** drop down list.
1. Find the **Silverpop Engage 2.0** icon and drag it to an empty plug-in slot in your Analytics report suite to launch the Data Connectors Integration Wizard.
1. 在Silverpop集成介绍页面上，查看文本，然后选中复选框以接受与集成相关的费用。
1. 选择要用于此集成的报表包。
1. Provide a friendly name to identify this integration, then click **[!UICONTROL Create and Configure this Integration]**.

   此页面提供该集成的概述，以及可帮助获取更多信息的有用链接。Adobe和Silverpop都有与此集成相关的费用。请联系这两个组织相应的销售代表，并确保您了解费用结构。
1. 在数据连接器集成向导的每个页面上，提供所需信息，如下表所示：

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>字段</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>配置部分</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>描述</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>集成名称 </p> </td> 
   <td colname="col03"> <p>(1)集成设置 </p> </td> 
   <td colname="col3"> <p>指定数据连接器显示在报表包的活动集成列表中的集成名称。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>下载文件 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p> 用于文件下载再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>用于无已知Silverpop ID的访客再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>帐户ID </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>Specify your Silverpop Account ID (the unique identifier assigned to your organization by Silverpop), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>表单名称 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>用于表单放弃再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>邮寄ID </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>(必需) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>(必需) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 跳出次数 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>(必需)指定“Analytics”(分析)事件，该事件存储从电子邮件系统导入的电子邮件总弹回数据。 </p> <p>“总退回次数”事件可让您查看由于交付问题而未发送给收件人的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Clicked </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>(必需)指定用于存储从电子邮件系统中导入的电子邮件单击数据的Analytics事件。 </p> <p>单击“单击”事件可查看单击该电子邮件的访客的数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 已下载文件 </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p> 用于文件下载再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 填写表单 </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>用于表单放弃再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 表单开始 </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>用于表单放弃再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已打开 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>(必需)指定用于存储通过电子邮件系统导入的电子邮件打开数据的Analytics事件。 </p> <p>打开的活动可让您查看打开电子邮件的访客的数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已发送 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>(必需)指定用于存储电子邮件从电子邮件系统导入的数据的Analytics事件。 </p> <p>通过“发送的活动”，可以查看发送的电子邮件的数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>取消订阅 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>(必需)指定用于存储从电子邮件系统中导入的电子邮件取消订阅数据的Analytics事件。 </p> <p>通过取消订阅活动，您可以查看打开电子邮件的访客数量，但单击取消订阅链接以退出单位以后的电子邮件消息。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>区段 </p> </td> 
   <td colname="col03"> <p>(3)数据设置 </p> </td> 
   <td colname="col3"> <p>此集成可创建合作伙伴定义区段中显示的合作伙伴定义区段。 </p> <p>此外，您还可以选择要包含在集成中的现有报表包级别区段。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>访问请求 </p> </td> 
   <td colname="col03"> <p>(3)数据设置 </p> </td> 
   <td colname="col3"> <p> (Required) Enable <span class="uicontrol"> Allow this integration to download product data</span>. </p> <p>可选：允许此集成下载收入、订单和单位。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>数据收集 </p> </td> 
   <td colname="col03"> <p>(3)数据设置 </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the s_code.js plug-in as the collection model for this integration (see <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"> Analytics Plug-In Code</a>). </p> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p>如果选择此选项，则指定用于此集成的唯一标识符： </p> <p> <b>消息ID查询字符串参数：</b>此值表示电子邮件合作伙伴附加到登录页面URL的消息ID。 </p> <p> <b>收件人ID查询字符串参数：</b> 此值表示电子邮件合作伙伴附加到登录页面URL的收件人ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>控制板和书签生成 </p> </td> 
   <td colname="col03"> <p>(4)报表设置 </p> </td> 
   <td colname="col3"> <p>自动生成集成的仪表板和书签。 </p> </td> 
  </tr> 
 </tbody> 
</table>

