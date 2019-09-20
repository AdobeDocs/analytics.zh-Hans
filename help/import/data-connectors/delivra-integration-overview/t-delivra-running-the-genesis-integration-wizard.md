---
description: 数据连接器集成向导将指导您完成数据连接器集成过程。
seo-description: 数据连接器集成向导将指导您完成数据连接器集成过程。
seo-title: 运行数据连接器集成向导
title: 运行数据连接器集成向导
uuid: 387ac9d0-3719-49ff-81cb-1f05accf9b6c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 运行数据连接器集成向导{#running-the-data-connectors-integration-wizard}

数据连接器集成向导将指导您完成数据连接器集成过程。

配置集成：

1. 登录到 Experience Cloud。
1. 在Analytics主页上，单击滚轮或工具栏上的Data Connectors™图标。
1. 在“数据连接器”页面上，选择要配置集成的报表包。

   >[!NOTE]
   >
   >确保从“数据连接器”页面左上角的 **“报表包** ”下拉列表中选择所需的报表包。

1. 单击 **Data Connectors** UI左侧“ **Partner List** ”（合作伙伴列表）顶部的“Selverty **”（字母顺序）选项卡，然后找到“Delivra** ”图标。
1. 将提 **交图标拖到** Analytics报告套件中的空插件插槽，以启动Data Connectors集成向导。
1. 在“交付集成简介”页面上，查看文本，选中复选框以接受与集成相关的费用，然后单击“下 **一步”**。

   此页面提供该集成的概述，以及可帮助获取更多信息的有用链接。与此集成相关的Adobe和交付费用。 请联系这两个组织相应的销售代表，并确保您了解费用结构。
1. 在数据连接器集成向导的每个页面上，提供所需的信息，如下表所述：

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
   <td colname="col3"> <p>指定数据连接器在报表包的“活动集成列表”中显示的集成名称。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>集成电子邮件地址 </p> </td> 
   <td colname="col3"> <p>指定接收与此集成相关的所有通知的电子邮件地址，然后单击 <b>下一步</b> ，以继续执行向导的步骤2。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>帐户ID </p> </td> 
   <td colname="col3"> <p>指定您的交付帐户ID（交付给您的组织的唯一标识符），然后单击 <b>Next</b> （下一步）以继续执行向导的步骤3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>消息ID </p> </td> 
   <td colname="col3"> <p>识别用于跟踪电子邮件ID的分析eVar。 </p> <p>消息ID用于营销／再营销活动。 消息ID通常称为“跟踪代码”。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>识别用于跟踪电子邮件收件人ID的分析eVar。 </p> <p>收件人ID用于营销／再营销活动。 消息ID通常称为“访客代码”。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>接受复选框 </p> </td> 
   <td colname="col3"> <p>复查“接受”复选框旁边显示的信息： </p> <p><i>我理解，通过启用“收件人ID”跟踪功能，此功能可跟踪我们网站访客的个人身份信息。 这涉及隐私问题，需要我所在的组织执行适当的程序，例如向我们的网站访客发出通知并征得其同意。 </i> </p> <p>如果您同意接受声明，请选中该复选框，然后单击“下 <b>一步</b> ”以继续执行向导的步骤4。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>客户定义的报表包级别区段 </p> </td> 
   <td colname="col3"> <p>此集成创建在集成向导的“集成区段”页面左侧显示的合作伙伴定义的区段。 </p> <p>此外，您还可以选择要包含在集成中的现有报表包级别区段。 </p> <p>在页面右侧选择所需的区段，然后单击下 <b>一步</b> ，继续执行向导的步骤5。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已单击 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件已点击数据的Analytics事件。 </p> <p>通过“已点击”事件，您可以查看点击电子邮件的访客数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已打开 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件“已打开”数据的Analytics事件。 </p> <p>通过“已打开”活动，您可以查看打开电子邮件的访客数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>已发送 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件已发送数据的分析事件。 </p> <p>单击事件可让您查看已发送的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>总弹回次数 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件总弹回次数数据的Analytics事件。 </p> <p>“总弹回次数”事件可让您查看由于传送问题而未发送给收件人的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>取消订阅 </p> </td> 
   <td colname="col3"> <p>指定用于存储从电子邮件系统导入的电子邮件取消订阅数据的Analytics事件。 </p> <p>通过取消订阅活动，您可以查看打开电子邮件但随后单击取消订阅链接以选择退出您组织的将来电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> 分享次数 </td> 
   <td colname="col3"> <p>指定将电子邮件共享到社交网络的次数，然后单击“下 <b>一步</b> ”以继续执行向导的步骤6。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>数据收集：JavaScript插件 </p> </td> 
   <td colname="col3"> <p>如果 <b>要将插件用作此集成的集合模型，请选择“</b> JavaScript插件” <b></b> ，然后单击“下一步”以继续执行向导的步骤7。 </p> <p> <p>注意： 自动解决方案是默认选择。 </p> </p> <p>请联系Adobe顾问以获取用于此集成的JavaScript插件副本。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>数据收集：自动化解决方案 </p> </td> 
   <td colname="col3"> <p>如果 <b>要为此集成使用自动收集模型</b> ，请选择自动化解决方案，然后指定用于此集成的唯一标识符。 </p> <p> <p>注意： 自动解决方案是默认选择。 </p> </p> <p>如果选择此选项，请指定用于此集成的唯一标识符： </p> <p><b>消息ID查询字符串参</b>数：此值表示电子邮件合作伙伴附加到登录页面URL的消息ID。 </p> <p><b></b> 收件人ID查询字符串参数：此值表示电子邮件合作伙伴附加到登录页面URL的收件人ID。 </p> <p>单击 <b>下一步</b> ，继续执行向导的步骤7。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>集成摘要 </p> </td> 
   <td colname="col3"> <p>单击每个类别旁边的加号(+)验证集成参数，然后单击 <b>Save</b> （保存）以继续执行向导的步骤8。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>集成完成 </p> </td> 
   <td colname="col3"> <p>单击 <b>完成</b> ，以完成集成。 </p> <p><b></b> 重要：在单击“完成”之前，Analytics不会保存集成 <b>设置</b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

