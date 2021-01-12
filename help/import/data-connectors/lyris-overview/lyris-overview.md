---
description: 描述通过集成实现的营销效率。
title: 适用于 Adobe Analytics 的 Lyris Data Connector
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 98%

---


# 适用于 Adobe Analytics 的 Lyris Data Connector{#lyris-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我们将于2021年8月1日终止Adobe数据连接器技术。 [了解更多...](/help/import/data-connectors/data-connectors-eol.md)

Adobe® Data Connectors™ 电子邮件集成将 Adobe Analytics 中的行为信息与 Lyris 电子邮件营销整合在一起，通过更相关的消息传送来重新定义成功衡量指标和目标受众。

向这些市场区段发送相关电子邮件，可能会带来全新的收入契机，从而在新电子邮件促销活动和现有电子邮件促销活动中提高转化率和收入。例如，经证实，根据访问期间查看的产品或放弃购买的产品发送相关电子邮件，可对收入产生显著影响，并且对成本的影响最小，因为这只是利用网站已获取的访客。

提高营销效率，是 Adobe Analytics 与 Lyris 集成的主要优势之一。此外，此集成会自动将电子邮件量度与 Adobe Analytics 数据同步（频率为每小时一次），以实现闭环报告。

## 主要优势和功能{#key-benefits-and-features}

介绍 Lyris 与 Adobe Marketing Reports and Analytics 集成的主要优势。

Lyris 与 Adobe Analytics 集成提供了以下主要优势：

* 将电子邮件营销数据与 Analytics 数据整合到一个报表界面中
* 通过转化为收入和促进网站取得成功，优化电子邮件促销活动
* 根据动态营销区段，向关键访客和市场区段进行再营销

### 动态营销区段

电子邮件集成支持动态营销区段，以帮助您推动业务发展。此集成具有以下开箱即用的营销区段：

* **放弃购买配置文件**：通过专门针对那些犹豫是否要完成购物的访客而设计的优化促销活动，帮助将这些访客转化为客户
* **购买配置文件**：通过按访客购买模式定位的促销活动，增加重复订单和提高平均订单价值
* **产品/内容查看行为配置文件**：通过基于产品查看和内容访问分析的营销区段，吸引潜在客户
* 客户还可以专门针对其用户需求创建和计划&#x200B;**自定义再营销区段**。

## 集成先决条件{#integration-prerequisites}

描述成功集成的先决条件。

在激活此集成之前，请针对您的 Adobe Analytics 部署和电子邮件软件查看以下项目。

这样做可确保在激活之前，遵循相应的最佳实践并满足相关先决条件，从而成功实现最佳集成。

### Adobe Analytics 先决条件 {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **特定于报表包**：请注意，此集成特定于报表包。在激活集成之前，请确保已选择所需的报表包
* **已配置的可用 Analytics 变量**：此集成需要自定义事件和自定义 eVar，以及可选的其他事件和其他 eVar。

* **授权代表**：请注意，根据您与 Adobe, Inc. 的服务协议或您与 Adobe 信任的某一合作伙伴的服务协议（如果适用），启用此集成可能会导致向贵公司收取相关费用。激活此集成，即表示您是贵公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **Adobe Analytics Data Warehouse**：此集成要求启用 Adobe Analytics Data Warehouse 才能生成再营销区段。如果尚未启用 Data Warehouse，请联系 Adobe 以了解详细信息。
* **收件人 ID**：此集成要求我们捕获“访客 ID”并将其存储在一个 Analytics 变量 (eVar) 中。访客 ID（通常称为“收件人 ID”）是 Lyris 系统中电子邮件地址的编码或数字表示形式。此“收件人 ID”与提取到 Lyris 系统中的网站下游访客行为（放弃购买、购买等）相关联，且可用于再营销。在设置过程中，当收到向导提示时，您必须为此确定一个 eVar。
* **外部跟踪**：如果您当前没有遵循为您发送的每个电子邮件促销活动启用外部跟踪这一最佳实践，则必须这样做以确保成功集成。有关详细信息，请参阅下面的 Lyris 部分
* **隐私合规**：您应该了解，启用“收件人 ID”或“访客 ID”跟踪功能，即表示该功能可能会跟踪您网站访客的个人身份信息。这会涉及隐私问题，需要贵组织实施适当的规程，例如，向网站访客发出通知并征得其同意。

### Lyris EmailLabs 先决条件 {#section-84abae9401224a3699fed861f715ebde}

* **有效的 Lyris 帐户**：要使用此 Data Connector 集成，您必须拥有有效的 Lyris 帐户。
* **帐户信息**：在此集成设置过程中，您需要提供关于自己 Lyris 帐户的以下信息：

   * *Lyris API 密钥*：用于填充数据
   * *查询字符串参数*：消息 ID 和收件人 ID（访客 ID）的这些参数会附加到登陆页面 URL 中。
   * *Lyris 服务器/URL*：您在 Lyris 系统中使用的服务器值
   * *Lyris 网站 ID*：也称为“客户 ID”，它是您的 Lyris HQ 实例的唯一值。此信息位于 EmailLabs“帐户主页”部分的“客户信息”下。

## 为 Lyris 配置 Adobe Analytics 变量{#configure-adobe-analytics-variables-for-lyris}

描述要为每个报表包实施保留的 eVar 和事件。

此集成要求为每个报表包实施至少保留 2 个 eVar。除了这些 eVar 之外，可能还需保留一些事件，具体取决于您要在 Analytics 中查看的 Lyris 数据。下表介绍了这些 eVar 和事件：

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量类型 </th> 
   <th colname="col2" class="entry"> 变量名称 </th> 
   <th colname="col3" class="entry"> 变量用途 </th> 
   <th colname="col4" class="entry"> 设置 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 消息 ID </td> 
   <td colname="col3"> 用于捕获单个电子邮件促销活动标识 </td> 
   <td colname="col4"> <p>状态：已启用 </p> <p>分配：最近 </p> <p>过期时间：“业务决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 电子邮件收件人 ID </td> 
   <td colname="col3"> 用于捕获点击了电子邮件促销活动的客户的匿名标识 </td> 
   <td colname="col4"> <p>状态：已启用 </p> <p>分配：最近 </p> <p>过期时间：“业务决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 发送的电子邮件 </td> 
   <td colname="col3"> 用于存储从 Lyris 发送的电子邮件数量 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 打开的电子邮件 </td> 
   <td colname="col3"> 用于存储打开的电子邮件数量 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 打开的唯一电子邮件 </td> 
   <td colname="col3"> 用于存储打开的唯一电子邮件数量 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 电子邮件点进次数 </td> 
   <td colname="col3"> 用于存储任何电子邮件的点击次数 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 电子邮件退回 </td> 
   <td colname="col3"> 用于存储退回的电子邮件数量 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 电子邮件取消订阅 </td> 
   <td colname="col3"> 用于存储禁用的电子邮件订阅数量 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
 </tbody> 
</table>
