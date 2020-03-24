---
description: Data Connectors 集成向导会引导您逐步完成 Data Connectors 集成流程。
title: 运行 Data Connectors 集成向导
uuid: 714417f7-c1df-4e61-a07f-d319f6581c9c
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 运行 Data Connectors 集成向导{#running-the-data-connectors-integration-wizard}

Data Connectors 集成向导会引导您逐步完成 Data Connectors 集成流程。

要配置集成，请执行以下操作：

1. 登录到 Experience Cloud。
1. 在 Adobe Analytics 主页上，单击滚轮或工具栏上的 Data Connectors™ 图标。
1. 在“Data Connectors”页面上，选择要配置集成的报表包。

   >[!NOTE]
   >
   >确保从“Data Connectors”页面左上角的&#x200B;**报表包**&#x200B;下拉列表中选择所需的报表包。

1. 单击 Data Connectors UI 左侧的&#x200B;**合作伙伴列表**&#x200B;顶部的&#x200B;**按字母顺序**&#x200B;选项卡，然后找到 **Datran** 图标。
1. 将 **Datran** 图标拖动到 Adobe Analytics 报表包中的空插件插槽，以启动 Data Connectors 集成向导。

1. 在 Datran 集成简介页面上，查看文本，选中相应复选框以接受与集成相关的费用，然后单击&#x200B;**下一步**。

   此页面提供该集成的概述，以及可帮助获取更多信息的有用链接。使用此集成，Adobe 和 Datran 可能会收取费用。请联系这两个组织相应的销售代表，并确保您了解费用结构。
1. 在 Data Connectors 集成向导的每个页面上，提供下表所述的必需信息：

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>向导页码</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>字段</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>说明</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>集成名称 </p> </td> 
   <td colname="col3"> <p>指定 Data Connectors 在报表包的活动集成列表中显示的集成名称。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>集成电子邮件地址 </p> </td> 
   <td colname="col3"> <p>指定接收与此集成相关的所有通知的电子邮件地址，然后单击<b>下一步</b>以继续执行向导的步骤 2。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>帐户 ID </p> </td> 
   <td colname="col3"> <p>指定您的 Datran 帐户 ID（由 Datran 分配给贵组织的唯一标识符），然后单击<b>下一步</b>以继续执行向导的步骤 3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>消息 ID </p> </td> 
   <td colname="col3"> <p>识别用于跟踪电子邮件消息 ID 的 Adobe Analytics eVar。 </p> <p>消息 ID 用于营销/再营销活动。消息 ID 通常是指“跟踪代码”。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>收件人 ID </p> </td> 
   <td colname="col3"> <p>识别用于跟踪电子邮件收件人 ID 的 Adobe Analytics eVar。 </p> <p>收件人 ID 用于营销/再营销活动。消息 ID 通常是指“访客代码”。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>“接受”复选框 </p> </td> 
   <td colname="col3"> <p>查看“接受”复选框旁边显示的信息： </p> <p><i>我了解，启用“收件人 ID”跟踪功能，即表示该功能可能会跟踪网站访客的个人身份信息。这会涉及隐私问题，需要组织实施适当的规程，例如，向网站访客发出通知并征得其同意。</i> </p> <p>如果您同意接受声明，请选中该复选框，然后单击<b>下一步</b>以继续执行向导的步骤 4。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>客户定义的报表包级别区段 </p> </td> 
   <td colname="col3"> <p>此集成会创建在集成向导的“集成区段”页面左侧显示的合作伙伴定义的区段。 </p> <p>此外，您还可以选择要包含在集成中的现有报表包级别区段。 </p> <p>在页面右侧选择所需的区段，然后单击<b>下一步</b>以继续执行向导的步骤 5。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已点击 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件点击数据的 Adobe Analytics 事件。 </p> <p>“已点击”事件让您能够查看点击了电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已打开 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件打开数据的 Adobe Analytics 事件。 </p> <p>“已打开”事件让您能够查看打开了电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已发送 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件发送数据的 Adobe Analytics 事件。 </p> <p>“已发送”事件让您能够查看已发送的电子邮件数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>退回总计 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件退回总计数据的 Adobe Analytics 事件。 </p> <p>“退回总计”事件让您能够查看由于传输问题而未发送给收件人的电子邮件数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已取消订阅 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件取消订阅数据的 Adobe Analytics 事件。 </p> <p>“已取消订阅”事件让您能够查看以下访客的数量：打开了电子邮件，但随后单击“取消订阅”链接以选择退出接收贵组织今后的电子邮件。 </p> <p>单击“下一步”以继续执行向导的步骤 6。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>数据收集：JavaScript 插件 </p> </td> 
   <td colname="col3"> <p>如果要使用插件作为此集成的收集模型，请选择 <b>JavaScript 插件</b>，然后单击<b>下一步</b>以继续执行向导的步骤 7。 </p> <p> <p>注意：默认情况下将选择“自动解决方案”。 </p> </p> <p>请联系您的 Adobe 顾问，以获取用于此集成的 JavaScript 插件副本。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>数据收集：自动解决方案 </p> </td> 
   <td colname="col3"> <p>如果要为此集成使用自动收集模型，请选择<b>自动解决方案</b>，然后指定用于此集成的唯一标识符。 </p> <p> <p>注意：默认情况下将选择“自动解决方案”。 </p> </p> <p>如果选择此选项，请指定用于此集成的唯一标识符： </p> <p><b>消息 ID 查询字符串参数：</b>此值表示电子邮件合作伙伴附加到登陆页面 URL 的消息 ID。 </p> <p><b>收件人 ID 查询字符串参数：</b>此值表示电子邮件合作伙伴附加到登陆页面 URL 的收件人 ID。 </p> <p>单击<b>下一步</b>以继续执行向导的步骤 7。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>集成摘要 </p> </td> 
   <td colname="col3"> <p>单击每个类别旁边的加号 (+) 来验证集成参数，然后单击<b>保存</b>以继续执行向导的步骤 8。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>集成完成 </p> </td> 
   <td colname="col3"> <p>单击<b>完成</b>以完成集成。 </p> <p><b>重要信息：</b>在单击<b>完成</b>后，Adobe Analytics 才会保存集成设置。 </p> </td> 
  </tr> 
 </tbody> 
</table>
