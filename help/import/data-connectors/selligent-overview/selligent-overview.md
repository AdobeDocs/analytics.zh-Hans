---
description: 'null'
solution: Analytics
title: Selligent Data Connector for Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Selligent Data Connector for Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

此集成包括以下主要优点：

* 将电子邮件营销和分析数据整合到一个报告界面中。
* 通过转化率和对收入和网站成功贡献来优化电子邮件营销活动。
* 根据动态营销细分，对关键访客和市场细分进行再营销。

## 动态营销细分 {#section-a2216f3339304636bd5417249bd635a4}

此电子邮件集成支持动态营销细分，以帮助您推动业务发展。 此集成具有以下开箱即用的营销细分：

| 区段 | 描述 |
|---|---|
| **购物车放弃资料** | 通过专门为犹豫是否完成购物车的客户设计的优化营销活动，帮助访客转化为客户。 |
| **购买配置文件** | 通过按访客购买模式定向的营销活动增加重复订购和平均订单价值。 |
| **产品／内容查看行为配置文件** | 根据产品视图和内容访问情况分析，通过营销细分接触潜在客户。 |
| **自定义再营销细分** | 客户还可以根据用户需求创建和计划自定义再营销细分。 |

## 激活此集成之前{#before-you-activate-this-integration}

在激活此集成之前，请根据您的Adobe Analytics部署和电子邮件软件检查以下项目。

这样做将确保在激活之前有适当的最佳实践和先决条件。 这将带来最佳和成功的集成。

## Adobe Analytics的先决条件{#prerequisites-for-adobe-analytics}

列出在部署集成之前，在Adobe Analytics中执行的必要操作。

| 先决条件 | 注释 |
|---|---|
| 选择报表包 | 请注意，此集成特定于报表包。 在激活集成之前，请确保已选择所需的报表包。 |
| 配置分析变量 | 此集成需要自定义事件和自定义eVar，以及可选的其他事件和其他eVar。 请参阅为Selligent配置分析变量。 |
| 授权代表 | 请注意，启用此集成可能会导致贵公司根据您与Adobe, Inc.的服务协议或您与Adobe信任的合作伙伴之一的服务协议（如果适用）产生费用。 通过激活此集成，您即表示您是您公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。 |
| 启用Adobe Data Warehouse™ | 此集成要求启用数据仓库才能生成再营销区段。 如果尚未启用Adobe数据仓库，请与Adobe联系以了解详细信息。 |
| Recipient ID | 该集成要求我们在Analytics变量(eVar)中捕获并存储“访客ID”。 访客ID（通常称为“收件人ID”）是来自Selligent系统的电子邮件地址的编码或数字表示形式。 此“收件人ID”与网站上的下游访客行为（购物车放弃、购买等）相关联它被拉回到Selligent系统中，并可用于再营销目的。 在设置过程中，当向导提示时，您必须为此标识eVar。 |
| 外部跟踪 | 如果您当前没有遵循为您发送的每个电子邮件营销活动启用外部跟踪的最佳实践，则必须这样做以确保成功集成。 有关详细信息，请参阅下面的“智能”部分。 |
| 隐私合规性 | 您应该了解，通过启用“收件人”或“访客ID”跟踪功能，可跟踪网站访客的个人身份信息。 这涉及隐私问题，需要贵组织实施适当的程序，例如向网站访客发出通知并征得其同意。 |

## 为Selligent配置分析变量{#configure-analytics-variables-for-selligent}

此集成要求为每个报表包实施保留2个eVar。

除了这些eVar之外，根据Selligent中的数据，可能会保留一些事件，您希望在Analytics中看到这些数据。 这些eVar和事件描述如下：

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量类型 </th> 
   <th colname="col2" class="entry"> 变量名称 </th> 
   <th colname="col3" class="entry"> 使用方式 </th> 
   <th colname="col4" class="entry"> 设置 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 消息ID </td> 
   <td colname="col3"> 要捕获单个电子邮件营销活动标识，请执行以下操作： </td> 
   <td colname="col4"> <p><b>状态</b>:已启用 </p> <p><b>分配</b>:最近 </p> <p><b>过期时间</b>:“业务决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> 为点击电子邮件营销活动的客户捕获匿名身份。 </td> 
   <td colname="col4"> <p><b>状态</b>:已启用 </p> <p><b>分配</b>:最近 </p> <p><b>过期时间</b>:“业务决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已发送 </td> 
   <td colname="col3"> 存储从Selligent发送的电子邮件数。 </td> 
   <td colname="col4"> <p><b>类型</b>:数字 </p> <p><b>参与</b>:已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 交付 </td> 
   <td colname="col3"> 存储已发送的电子邮件数。 </td> 
   <td colname="col4"> <p><b>类型</b>:数字 </p> <p><b>参与</b>:已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 查看次数 </td> 
   <td colname="col3"> 存储查看的唯一电子邮件数。 </td> 
   <td colname="col4"> <p><b>类型</b>:数字 </p> <p><b>参与</b>:已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 点击次数 </td> 
   <td colname="col3"> 存储任何电子邮件被点击的次数。 </td> 
   <td colname="col4"> <p><b>类型</b>:数字 </p> <p><b>参与</b>:已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 退回 </td> 
   <td colname="col3"> 存储退回的电子邮件数。 </td> 
   <td colname="col4"> <p><b>类型</b>:数字 </p> <p><b>参与</b>:已启用 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Selligent的先决条件{#prerequisites-for-selligent}

列出在部署集成之前要从您的Selligent帐户提供的必要信息。

**有效的Selligent帐户**

要使用此数据连接器集成，您必须拥有有效的Selligent帐户。

**帐户信息**

在此集成设置过程中，您需要以下关于您的Selligent帐户的信息：

* **Adobe服务URL**:

   该URL可以从用于登录到Selligent Marketing解决方案的URL派生。 将url的“/simweb/login.aspx”部分替换为“/automation/omniture.asmx”

   E.g: `http://<client-specific install url>/automation/omniture.asmx`

* **** 查询字符串参数：这些内容会附加到邮件ID和收件人ID（访客ID）的登录页面URL中。 这些ID始终分别为MID和RID，用于消息ID和收件人ID。

* **集成令牌** 从Simweb中启动Manager工具，然后转到 **[!UICONTROL Configuration]** &gt; **[!UICONTROL System Settings]** &gt; **[!UICONTROL General]******&#x200B;选项卡&gt; System System。 在“安 **[!UICONTROL 全性]**”下，您可以找到集成令牌。

   ![](assets/selligent-integration_token.png)
