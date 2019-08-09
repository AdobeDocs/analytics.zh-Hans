---
description: 数据连接器集成向导将指导您逐步完成数据连接器集成过程。
seo-description: 数据连接器集成向导将指导您逐步完成数据连接器集成过程。
seo-title: 运行数据连接器集成向导
title: 运行数据连接器集成向导
uuid: 714417f7-c1 df-4e61 f-d319 f6581 c9 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 运行数据连接器集成向导{#running-the-data-connectors-integration-wizard}

数据连接器集成向导将指导您逐步完成数据连接器集成过程。

配置集成：

1.  登录到 Marketing Cloud。
1. 在Adobe Analytics主页上，单击风车或工具栏上的数据连接器™图标。
1. 在“数据连接器”页面上，选择要配置集成的报表包。

   >[!NOTE]
   >
   >确保从“数据连接器”页面左上角的 **“报表包** ”下拉列表中选择所需的报表包。

1. 单击数据 **连接器** UI左侧“ **合作伙伴列表** ”顶部的“字母顺序”选项卡，然后找到 **“数据点** ”图标。
1. 将 **Datan** 图标拖到Adobe Analytics报告套件中的空插件槽中，启动数据连接器集成向导。

1. 在“Datan Integration integration”(数据点集成)介绍页面上，查看文本，然后选中该复选框以接受与集成相关的费用，然后单击 **下一**&#x200B;步。

   此页面提供该集成的概述，以及可帮助获取更多信息的有用链接。与此集成相关的Adobe和Datrun费用均有。请联系这两个组织相应的销售代表，并确保您了解费用结构。
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
   <td colname="col3"> <p>指定接收与此集成相关的所有通知的电子邮件地址，然后单击 <b>下一步</b> 以继续执行向导的步骤2。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>帐户ID </p> </td> 
   <td colname="col3"> <p>指定日期帐户ID(由Datan分配给您的组织的唯一标识符)，然后单击 <b>下一步</b> 以继续执行向导的步骤3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>消息ID </p> </td> 
   <td colname="col3"> <p>识别用于跟踪电子邮件ID的Adobe Analytics eVar。 </p> <p>消息ID用于营销/再营销活动。消息ID通常称为“跟踪代码”。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>识别用于跟踪电子邮件收件人ID的Adobe Analytics eVar。 </p> <p>收件人ID用于营销/再营销活动。消息ID通常称为“访客代码”。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>接受复选框 </p> </td> 
   <td colname="col3"> <p>查看“接受”复选框旁边显示的信息： </p> <p><i>我了解，通过启用“收件人ID”跟踪功能，此功能可跟踪我们网站访客的个人识别信息。这涉及到隐私权事项，需要我的组织实施适当程序，例如向网站访客提供通知和同意。 </i> </p> <p>如果您同意接受声明，请选中该复选框，然后单击 <b>下一步</b> 以继续执行向导的步骤4。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>客户端定义的报表包级别区段 </p> </td> 
   <td colname="col3"> <p>此集成创建了合作伙伴定义的区段，显示在集成向导的“集成区段”页面左侧。 </p> <p>此外，您还可以选择要包含在集成中的现有报表包级别区段。 </p> <p>在页面右侧选择所需的区段，然后单击 <b>下一步</b> 以继续执行向导的步骤5。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clicked </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统中导入的电子邮件单击数据的Adobe Analytics事件。 </p> <p>单击“单击”事件可查看单击该电子邮件的访客的数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已打开 </p> </td> 
   <td colname="col3"> <p>指定用于存储通过电子邮件系统导入的电子邮件打开数据的Adobe Analytics事件。 </p> <p>打开的活动可让您查看打开电子邮件的访客的数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已发送 </p> </td> 
   <td colname="col3"> <p>指定存储通过电子邮件系统导入的电子邮件的Adobe Analytics事件。 </p> <p>单击“单击”事件可查看发送的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>退回总次数 </p> </td> 
   <td colname="col3"> <p>指定Adobe Analytics事件，用于存储从电子邮件系统导入的电子邮件总退回数据。 </p> <p>“总退回次数”事件可让您查看由于交付问题而未发送给收件人的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>取消订阅 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统中导入的电子邮件取消订阅数据的Adobe Analytics事件。 </p> <p>通过取消订阅活动，您可以查看打开电子邮件的访客数量，但单击取消订阅链接以退出单位以后的电子邮件消息。 </p> <p>单击下一步以继续执行向导的步骤6。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>数据收集：JavaScript插件 </p> </td> 
   <td colname="col3"> <p>如果要使用该插件作为此集成的集合模型，请选择 <b></b> JavaScript插件，然后单击 <b>下一步</b> 以继续执行向导的步骤7。 </p> <p> <p>注意：自动解决方案是默认选择。 </p> </p> <p>联系您的Adobe顾问以获取用于此集成的JavaScript插件副本。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>数据收集：自动化解决方案 </p> </td> 
   <td colname="col3"> <p>如果您要将自动收集模型用于此集成，请选择 <b>“自动解决方案</b> ”，然后指定用于此集成的唯一标识符。 </p> <p> <p>注意：自动解决方案是默认选择。 </p> </p> <p>如果选择此选项，则指定用于此集成的唯一标识符： </p> <p><b>消息ID查询字符串参数：</b>此值表示电子邮件合作伙伴附加到登录页面URL的消息ID。 </p> <p><b>收件人ID查询字符串参数：</b> 此值表示电子邮件合作伙伴附加到登录页面URL的收件人ID。 </p> <p>单击 <b>下一</b> 步以继续执行向导的步骤7。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>集成摘要 </p> </td> 
   <td colname="col3"> <p>单击每个类别旁边的加号(+)验证集成参数，然后单击 <b>保存</b> 以继续执行向导的步骤8。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>集成完成 </p> </td> 
   <td colname="col3"> <p>单击 <b>“完成</b> ”以完成集成。 </p> <p><b>重要说明：</b> 在单击 <b>“完成</b>”之前，Adobe Analytics才会保存集成设置。 </p> </td> 
  </tr> 
 </tbody> 
</table>

