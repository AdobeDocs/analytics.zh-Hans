---
description: 数据连接器集成向导将指导您完成数据连接器集成过程。
seo-description: 数据连接器集成向导将指导您完成数据连接器集成过程。
seo-title: Silverpop集成
title: Silverpop集成
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Silverpop集成{#silverpop-integration}

数据连接器集成向导将指导您完成数据连接器集成过程。

配置集成：

1. 在Adobe Experience cloud中，从产品下拉列表中选择数据连接器™。
1. 单击 **[!UICONTROL 新增]** ，然后在显 **[!UICONTROL 示下拉列表中选]** 择按名称 **** 。
1. 查找 **Silverpop Engage 2.0** 图标，并将其拖动到Analytics报告套件中的空插件插槽中，以启动Data Connectors集成向导。
1. 在Silverpop集成简介页面上，查看文本，然后选中复选框以接受与集成相关的费用。
1. 选择要用于此集成的报表包。
1. 提供一个易记名称以标识此集成，然后单击创 **[!UICONTROL 建和配置此集成]**。

   此页面提供该集成的概述，以及可帮助获取更多信息的有用链接。与此集成相关的是Adobe和Silverpop费用。 请联系这两个组织相应的销售代表，并确保您了解费用结构。
1. 在数据连接器集成向导的每个页面上，提供所需的信息，如下表所述：

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
   <td colname="col3"> <p>指定数据连接器在报表包的“活动集成列表”中显示的集成名称。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>下载文件 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p> 用于文件下载再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>用于向没有已知Silverpop ID的访客进行再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>帐户ID </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>指定您的Silverpop帐户ID（Silverpop为您的组织分配的唯一标识符），然后单击 <b>Next</b> （下一步）以继续执行向导的步骤3。 </p> </td> 
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
   <td colname="col3"> <p>（必需）指定存储从电子邮件系统导入的电子邮件总弹回次数数据的Analytics事件。 </p> <p>“总弹回次数”事件可让您查看由于传送问题而未发送给收件人的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已单击 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件已点击数据的Analytics事件。 </p> <p>通过“已点击”事件，您可以查看点击电子邮件的访客数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 已下载文件 </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p> 用于文件下载再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 表单已完成 </td> 
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
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件已打开数据的Analytics事件。 </p> <p>通过“已打开”活动，您可以查看打开电子邮件的访客数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已发送 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件已发送数据的Analytics事件。 </p> <p>通过“已发送”活动，您可以查看已发送的电子邮件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>取消订阅 </p> </td> 
   <td colname="col03"> <p>(2)变量映射 </p> </td> 
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件取消订阅数据的Analytics事件。 </p> <p>通过取消订阅活动，您可以查看打开电子邮件但随后单击取消订阅链接以选择退出您组织的将来电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>区段 </p> </td> 
   <td colname="col03"> <p>（三）数据设置 </p> </td> 
   <td colname="col3"> <p>此集成创建在“合作伙伴区段”部分中显示的合作伙伴定义的区段。 </p> <p>此外，您还可以选择要包含在集成中的现有报表包级别区段。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 访问请求 </p> </td> 
   <td colname="col03"> <p>（三）数据设置 </p> </td> 
   <td colname="col3"> <p> （必需）启用 <span class="uicontrol"> 允许此集成下载产品数据</span>。 </p> <p>可选：允许此集成下载收入、订单和件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>数据收集 </p> </td> 
   <td colname="col03"> <p>（三）数据设置 </p> </td> 
   <td colname="col3"> <p>如果 <b>要将s_code.js插件用作此集成的收集模型，请选择“</b> JavaScript插件”(请参阅分析插件代码 <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"></a>)。 </p> <p>如果 <b>要为此集成使用自动收集模型</b> ，请选择自动化解决方案，然后指定用于此集成的唯一标识符。 </p> <p>如果选择此选项，请指定用于此集成的唯一标识符： </p> <p> <b>消息ID查询字符串参</b>数：此值表示电子邮件合作伙伴附加到登录页面URL的消息ID。 </p> <p> <b></b> 收件人ID查询字符串参数：此值表示电子邮件合作伙伴附加到登录页面URL的收件人ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>功能板和书签生成 </p> </td> 
   <td colname="col03"> <p>（四）报告设置 </p> </td> 
   <td colname="col3"> <p>自动生成功能板和书签以进行集成。 </p> </td> 
  </tr> 
 </tbody> 
</table>

