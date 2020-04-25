---
description: Data Connectors 集成向导会引导您逐步完成 Data Connectors 集成流程。
title: Silverpop 集成
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Silverpop 集成{#silverpop-integration}

Data Connectors 集成向导会引导您逐步完成 Data Connectors 集成流程。

要配置集成，请执行以下操作：

1. 在 Adobe Experience Cloud 中，从产品下拉列表中选择 Data Connectors™。
1. 单击&#x200B;**[!UICONTROL 新增]**，然后在&#x200B;**[!UICONTROL 显示]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 按名称]**。
1. 查找 **Silverpop Engage 2.0** 图标，并将其拖动到 Analytics 报表包中的空插件插槽，以启动 Data Connectors 集成向导。
1. 在 Silverpop 集成简介页面上，查看文本，然后选中相应复选框以接受与集成相关的费用。
1. 选择要用于此集成的报表包。
1. 提供一个用于标识此集成的易记名称，然后单击&#x200B;**[!UICONTROL 创建并配置此集成]**。

   此页面提供该集成的概述，以及可帮助获取更多信息的有用链接。使用此集成，Adobe 和 Silverpop 可能会收取费用。请联系这两个组织相应的销售代表，并确保您了解费用结构。
1. 在 Data Connectors 集成向导的每个页面上，提供下表所述的必需信息：

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
   <td colname="col03"> <p>(1) 集成设置 </p> </td> 
   <td colname="col3"> <p>指定 Data Connectors 在报表包的活动集成列表中显示的集成名称。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>下载文件 </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p> 用于文件下载再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 电子邮件地址 </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>用于向没有已知 Silverpop ID 的访客进行再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>帐户 ID </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>指定您的 Silverpop 帐户 ID（由 Silverpop 分配给贵组织的唯一标识符），然后单击<b>下一步</b>以继续执行向导的步骤 3。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>表单名称 </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>用于表单放弃再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>邮件 ID </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>（必需） </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>（必需） </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 退回 </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件退回总计数据的 Analytics 事件。 </p> <p>“退回总计”事件让您能够查看由于传输问题而未发送给收件人的电子邮件数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已点击 </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件点击数据的 Analytics 事件。 </p> <p>“已点击”事件让您能够查看点击了电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 已下载文件 </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p> 用于文件下载再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 已完成表单 </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>用于表单放弃再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> 已开始表单 </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>用于表单放弃再营销。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已打开 </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件打开数据的 Analytics 事件。 </p> <p>“已打开”事件让您能够查看打开了电子邮件的访客数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已发送 </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件发送数据的 Analytics 事件。 </p> <p>“已发送”事件让您能够查看已发送的电子邮件数量。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>已取消订阅 </p> </td> 
   <td colname="col03"> <p>(2) 变量映射 </p> </td> 
   <td colname="col3"> <p>（必需）指定用于存储从电子邮件系统导入的电子邮件取消订阅数据的 Analytics 事件。 </p> <p>“已取消订阅”事件让您能够查看以下访客的数量：打开了电子邮件，但随后单击“取消订阅”链接以选择退出接收贵组织今后的电子邮件。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>区段 </p> </td> 
   <td colname="col03"> <p>(3) 数据设置 </p> </td> 
   <td colname="col3"> <p>此集成会创建在“合作伙伴区段”部分中显示的合作伙伴定义的区段。 </p> <p>此外，您还可以选择要包含在集成中的现有报表包级别区段。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>访问请求 </p> </td> 
   <td colname="col03"> <p>(3) 数据设置 </p> </td> 
   <td colname="col3"> <p> （必需）启用“<span class="uicontrol">允许此集成下载产品数据</span>”。 </p> <p>可选：允许此集成下载收入、订单和件数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>数据收集 </p> </td> 
   <td colname="col03"> <p>(3) 数据设置 </p> </td> 
   <td colname="col3"> <p>如果要使用 s_code.js 插件作为此集成的收集模型，请选择 <b>JavaScript 插件</b>（请参阅 <a href="../silverpop-overview/silverpop-analytics-code.md">Analytics 插件代码</a>）。 </p> <p>如果要为此集成使用自动收集模型，请选择<b>自动解决方案</b>，然后指定用于此集成的唯一标识符。 </p> <p>如果选择此选项，请指定用于此集成的唯一标识符： </p> <p> <b>消息 ID 查询字符串参数：</b>此值表示电子邮件合作伙伴附加到登陆页面 URL 的消息 ID。 </p> <p> <b>收件人 ID 查询字符串参数：</b>此值表示电子邮件合作伙伴附加到登陆页面 URL 的收件人 ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>功能板和书签生成 </p> </td> 
   <td colname="col03"> <p>(4) 报表设置 </p> </td> 
   <td colname="col3"> <p>自动为集成生成功能板和书签。 </p> </td> 
  </tr> 
 </tbody> 
</table>

