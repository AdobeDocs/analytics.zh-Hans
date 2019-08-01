---
description: 数据连接器集成向导将指导您逐步完成数据连接器集成过程。
seo-description: 数据连接器集成向导将指导您逐步完成数据连接器集成过程。
seo-title: 运行数据连接器集成向导
title: 运行数据连接器集成向导
uuid: 387ac9d0-3719-49ff-81cb-1f05acf9b6c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d55b23a5baf5be1d7afb708cc6ef94851eac3e77

---


# Running the Data Connectors Integration Wizard{#running-the-data-connectors-integration-wizard}

数据连接器集成向导将指导您逐步完成数据连接器集成过程。

配置集成：

1.  登录到 Marketing Cloud。
1. 在Analytics主页上，单击风车或工具栏上的数据连接器™图标。
1. 在“数据连接器”页面上，选择要配置集成的报表包。

   >[!NOTE]
   >
   >Make sure that you select the desired report suite from the **Report Suite** drop-down list in the upper-left corner of the Data Connectors page.

1. Click the **Alphabetical** tab at the top of the **Partner List** on the left side of the Data Connectors UI, then locate the **Delivra** icon.
1. Drag the **Delivra** icon to an empty plug-in slot in your Analytics report suite to launch the Data Connectors Integration Wizard.
1. On the Delivra Integration introduction page, review the text, then select the check box to accept the fees associated with the integration, then click **Next**.

   此页面提供该集成的概述，以及可帮助获取更多信息的有用链接。Adobe和Delivra都有与此集成相关的费用。请联系这两个组织相应的销售代表，并确保您了解费用结构。
1. 在数据连接器集成向导的每个页面上，提供所需信息，如下表所示：

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>向导PAGE#</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>Field</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPTION</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>集成名称 </p> </td> 
   <td colname="col3"> <p>指定数据连接器显示在报表包的活动集成列表中的集成名称。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>集成电子邮件地址 </p> </td> 
   <td colname="col3"> <p>Specify the email address that receives all notifications related to this integration, then click <b>Next</b> to proceed to Step 2 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>帐户ID </p> </td> 
   <td colname="col3"> <p>Specify your Delivra Account ID (the unique identifier assigned to your organization by Delivra), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>消息ID </p> </td> 
   <td colname="col3"> <p>标识用于跟踪电子邮件ID的Analytics eVar。 </p> <p>消息ID用于营销/再营销活动。消息ID通常称为“跟踪代码”。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>识别用于跟踪电子邮件收件人ID的Analytics eVar。 </p> <p>收件人ID用于营销/再营销活动。消息ID通常称为“访客代码”。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>接受复选框 </p> </td> 
   <td colname="col3"> <p>查看“接受”复选框旁边显示的信息： </p> <p><i>我了解，通过启用“收件人ID”跟踪功能，此功能可跟踪我们网站访客的个人识别信息。This has privacy implications requiring the implementation of appropriate procedures by my organization, such as providing notice to, and consent of, our site visitors. </i> </p> <p>If you agree to the acceptance statement, select the check box, then click <b>Next</b> to proceed to Step 4 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>客户端定义的报表包级别区段 </p> </td> 
   <td colname="col3"> <p>此集成创建了合作伙伴定义的区段，显示在集成向导的“集成区段”页面左侧。 </p> <p>此外，您还可以选择要包含在集成中的现有报表包级别区段。 </p> <p>Select the desired segments on the right side of the page, then click <b>Next</b> to proceed to Step 5 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clicked </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统中导入的电子邮件单击数据的Analytics事件。 </p> <p>单击“单击”事件可查看单击该电子邮件的访客的数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已打开 </p> </td> 
   <td colname="col3"> <p>指定用于存储通过电子邮件系统导入的电子邮件打开数据的Analytics事件。 </p> <p>打开的活动可让您查看打开电子邮件的访客的数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已发送 </p> </td> 
   <td colname="col3"> <p>指定用于存储电子邮件从电子邮件系统导入的数据的Analytics事件。 </p> <p>单击“单击”事件可查看发送的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>退回总次数 </p> </td> 
   <td colname="col3"> <p>指定“Analytics”(分析)事件，用于存储从电子邮件系统导入的电子邮件总弹回数据。 </p> <p>“总退回次数”事件可让您查看由于交付问题而未发送给收件人的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>取消订阅 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统中导入的电子邮件取消订阅数据的Analytics事件。 </p> <p>通过取消订阅活动，您可以查看打开电子邮件的访客数量，但单击取消订阅链接以退出单位以后的电子邮件消息。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> 分享次数 </td> 
   <td colname="col3"> <p>Specify the number of times the email message was shared to a social network, then click <b>Next</b> to proceed to Step 6 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>数据收集：JavaScript插件 </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the plug-in as the collection model for this integration, then click <b>Next</b> to proceed to Step 7 of the Wizard. </p> <p> <p>注意：自动解决方案是默认选择。 </p> </p> <p>联系您的Adobe顾问以获取用于此集成的JavaScript插件副本。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>数据收集：自动化解决方案 </p> </td> 
   <td colname="col3"> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p> <p>注意：自动解决方案是默认选择。 </p> </p> <p>如果选择此选项，则指定用于此集成的唯一标识符： </p> <p><b>消息ID查询字符串参数：</b>此值表示电子邮件合作伙伴附加到登录页面URL的消息ID。 </p> <p><b>收件人ID查询字符串参数：</b> 此值表示电子邮件合作伙伴附加到登录页面URL的收件人ID。 </p> <p>Click <b>Next</b> to proceed to Step 7 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>集成摘要 </p> </td> 
   <td colname="col3"> <p>Verify the integration parameters by clicking the plus sign (+) next to each category, then click <b>Save</b> to proceed to Step 8 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>集成完成 </p> </td> 
   <td colname="col3"> <p>Click <b>Finish</b> to complete the integration. </p> <p><b>重要说明：</b> 在单击 <b>“完成</b>”之前，Analytics才会保存集成设置。 </p> </td> 
  </tr> 
 </tbody> 
</table>

