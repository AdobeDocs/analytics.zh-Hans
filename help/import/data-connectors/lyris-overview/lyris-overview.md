---
description: 描述通过集成实现的营销效率。
solution: Analytics
title: Lyris Data Connector for Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Lyris Data Connector for Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

描述通过集成实现的营销效率。

Adobe® Data Connectors™电子邮件集成将Adobe Analytics的行为信息与Lyris电子邮件营销相结合，重新定义成功衡量并通过更相关的消息定位受众。

向这些市场领域提供相关电子邮件可能会带来全新的收入机会，从而在新电子邮件和现有电子邮件营销活动中提高转化率和收入。 例如，根据访问期间查看的产品或放弃购物车中的产品发送相关电子邮件已证明对收入产生显着影响，并且对成本的影响最小，因为这只是利用您的网站已获得的访客。

营销效率的提高是将Adobe Analytics与Lyris集成的主要优势之一。 此外，此集成将自动将电子邮件指标与Adobe Analytics数据同步，频率与闭环报告每小时相同。

## 主要优势和功能{#key-benefits-and-features}

介绍集成Lyris和Adobe Marketing Reports and Analytics的主要优势。

Lyris与Adobe Analytics的集成提供了以下主要优势：

* 将电子邮件营销和分析数据整合到一个报告界面中
* 通过转化率和对收入和网站成功贡献来优化电子邮件营销活动
* 根据动态营销细分，向关键访客和市场细分进行再营销

### 动态营销细分

电子邮件集成支持动态营销细分，以帮助您推动业务发展。 此集成具有以下开箱即用的营销细分：

* **购物车放弃资料**:通过专门为犹豫是否完成购物车的访客设计的优化营销活动，帮助访客转化为客户
* **购买配置文件**:通过按访客购买模式定向的营销活动增加重复订单和平均订单价值
* **产品／内容查看行为配置文件**:根据产品视图和内容访问情况分析通过营销细分接触潜在客户
* 客户还可以根据用 **户需求创建和计划自定义再营销** 细分。

## 集成先决条件{#integration-prerequisites}

描述成功集成的先决条件。

在激活此集成之前，请根据Adobe Analytics和电子邮件软件的部署查看以下项目。

这可确保在激活之前制定适当的最佳实践和先决条件，这将导致最佳和成功的集成。

### Adobe Analytics的先决条件 {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **报告包特定**:请注意，此集成特定于报表包。 在激活集成之前，请确保已选择所需的报表包
* **可用和配置的Analytics变量**:此集成需要自定义事件和自定义eVar，以及可选的其他事件和其他eVar。

* **授权代表**:请注意，启用此集成可能会导致贵公司根据您与Adobe, Inc.的服务协议或您与Adobe信任的合作伙伴之一的服务协议（如果适用）产生费用。 通过激活此集成，您即表示您是您公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **Adobe Analytics数据仓库**:此集成要求启用Adobe Analytics数据仓库以生成再营销细分。 如果尚未启用数据仓库，请与Adobe联系以了解详细信息。
* **收件人ID**:该集成要求我们在Analytics变量(eVar)中捕获并存储“访客ID”。 访客ID（通常称为“收件人ID”）是Lyris系统中电子邮件地址的编码或数字表示形式。 此“收件人ID”与网站上的下游访客行为（购物车放弃、购买等）相关联被拉回Lyris系统，可用于再营销目的。 在设置过程中，当向导提示时，您必须为此标识eVar。
* **外部跟踪**:如果您当前没有遵循为您发送的每个电子邮件营销活动启用外部跟踪的最佳实践，则必须这样做以确保成功集成。 有关详细信息，请参阅下面的Lyris部分
* **隐私合规**:您应该了解，通过启用“收件人”或“访客ID”跟踪功能，可跟踪网站访客的个人身份信息。 这会涉及隐私问题，需要贵组织执行适当的程序，例如向网站访客发出通知并征得其同意。

### Lyris emailLabs的先决条件 {#section-84abae9401224a3699fed861f715ebde}

* **有效的Lyris帐户**:要使用此Data Connector集成，您必须拥有有效的Lyris帐户。
* **帐户信息**:在此集成设置过程中，您需要以下Lyris帐户的相关信息：

   * *Lyris API密钥*:用于数据填充
   * *查询字符串参数*:这些内容会附加到邮件ID和收件人ID（访客ID）的登录页面URL中。
   * *Lyris Server/URL*:您在Lyris系统中使用的服务器值
   * *Lyris站点ID*:这也称为“客户ID”，它是Lyris HQ实例的唯一值。 此信息位于EmailLabs“帐户主页”部分的“客户信息”下。

## 为Lyris配置Adobe Analytics变量{#configure-adobe-analytics-variables-for-lyris}

描述要为每个报表包实施保留的eVar和事件。

此集成要求为每个报表包实施至少保留2个eVar。 除了这些eVar之外，可能会保留一些事件，具体取决于您要在Analytics中查看的Lyris数据。 下表介绍了这些eVar和事件：

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量类型 </th> 
   <th colname="col2" class="entry"> 变量名称 </th> 
   <th colname="col3" class="entry"> 变量的使用方式 </th> 
   <th colname="col4" class="entry"> 设置 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 消息ID </td> 
   <td colname="col3"> 要捕获单个电子邮件营销活动标识，请执行以下操作： </td> 
   <td colname="col4"> <p>状态：已启用 </p> <p>分配：最近 </p> <p>过期时间：“业务决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> 为点击电子邮件营销活动的客户捕获匿名身份 </td> 
   <td colname="col4"> <p>状态：已启用 </p> <p>分配：最近 </p> <p>过期时间：“业务决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 已发送电子邮件 </td> 
   <td colname="col3"> 存储否。 从Lyris发送的电子邮件 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 已打开电子邮件 </td> 
   <td colname="col3"> 存储否。 打开的电子邮件 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 打开的唯一电子邮件 </td> 
   <td colname="col3"> 存储否。 打开的独特电子邮件 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 电子邮件点进次数 </td> 
   <td colname="col3"> 存储否。 点击任何电子邮件的次数 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 电子邮件弹回次数 </td> 
   <td colname="col3"> 存储否。 那些邮件 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 取消订阅电子邮件 </td> 
   <td colname="col3"> 存储否。 已禁用的电子邮件订阅 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
 </tbody> 
</table>
