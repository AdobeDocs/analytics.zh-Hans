---
description: 'null'
title: 适用于 Adobe Analytics 的 Selligent Data Connector
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 98%

---


# 适用于 Adobe Analytics 的 Selligent Data Connector{#selligent-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我们将于2021年8月1日终止Adobe数据连接器技术。 [了解更多...](/help/import/data-connectors/data-connectors-eol.md)

此集成具有以下主要优势：

* 将电子邮件营销数据与 Analytics 数据整合到一个报表界面中。
* 通过转化为收入和促进网站取得成功，优化电子邮件促销活动。
* 根据动态营销区段，向关键访客和市场区段进行再营销。

## 动态营销区段 {#section-a2216f3339304636bd5417249bd635a4}

此电子邮件集成支持动态营销区段，以帮助您推动业务发展。此集成具有以下开箱即用的营销区段：

| 区段 | 描述 |
|---|---|
| **放弃购买配置文件** | 通过专门针对那些犹豫是否要完成购物的访客而设计的优化促销活动，帮助将这些访客转化为客户。 |
| **购买配置文件** | 通过按访客购买模式定位的促销活动，增加重复订单和提高平均订单价值。 |
| **产品/内容查看行为配置文件** | 通过基于产品查看和内容访问分析的营销区段，吸引潜在客户。 |
| **自定义再营销区段** | 客户还可以专门针对其用户需求创建和计划自定义再营销区段。 |

## 在激活此集成之前{#before-you-activate-this-integration}

在激活此集成之前，请针对您的 Adobe Analytics 部署和电子邮件软件查看以下项目。

这样做可确保在激活之前，遵循相应的最佳实践并满足相关先决条件，从而成功实现最佳集成。

## Adobe Analytics 先决条件{#prerequisites-for-adobe-analytics}

列出在部署集成之前必须在 Adobe Analytics 中执行的操作。

| 先决条件 | 注释 |
|---|---|
| 选择报表包 | 请注意，此集成特定于报表包。在激活集成之前，请确保已选择所需的报表包。 |
| 配置 Analytics 变量 | 此集成需要自定义事件和自定义 eVar，以及可选的其他事件和其他 eVar。请参阅“为 Selligent 配置 Analytics 变量”。 |
| 授权代表 | 请注意，根据您与 Adobe, Inc. 的服务协议或您与 Adobe 信任的某一合作伙伴的服务协议（如果适用），启用此集成可能会导致向贵公司收取相关费用。激活此集成，即表示您是贵公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。 |
| 启用 Adobe Data Warehouse™ | 此集成要求启用 Data Warehouse 以生成再营销区段。如果尚未启用 Adobe Data Warehouse，请联系 Adobe 以了解详细信息。 |
| 收件人 ID | 此集成要求我们捕获“访客 ID”并将其存储在一个 Analytics 变量 (eVar) 中。访客 ID（通常称为“收件人 ID”）是 Selligent 系统中电子邮件地址的编码或数字表示形式。此“收件人 ID”与提取到 Selligent 系统中的网站下游访客行为（放弃购买、购买等）相关联，且可用于再营销。在设置过程中，当收到向导提示时，您必须为此确定一个 eVar。 |
| 外部跟踪 | 如果您当前没有遵循为您发送的每个电子邮件促销活动启用外部跟踪这一最佳实践，则必须这样做以确保成功集成。有关详细信息，请参阅下面的 Selligent 部分。 |
| 隐私合规 | 您应该了解，启用“收件人 ID”或“访客 ID”跟踪功能，即表示该功能可能会跟踪您网站访客的个人身份信息。这会涉及隐私问题，需要贵组织实施适当的规程，例如，向网站访客发出通知并征得其同意。 |

## 为 Selligent 配置 Analytics 变量{#configure-analytics-variables-for-selligent}

此集成要求为每个报表包实施保留 2 个 eVar。

除了这些 eVar 之外，可能还需保留一些事件，具体取决于您要在 Analytics 中查看的 Selligent 数据。这些 eVar 和事件描述如下：

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
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
   <td colname="col3"> 用于捕获单个电子邮件促销活动标识。 </td> 
   <td colname="col4"> <p><b>状态</b>：已启用 </p> <p><b>分配</b>：最近 </p> <p><b>过期时间</b>：“业务决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 收件人 ID </td> 
   <td colname="col3"> 用于捕获点击了电子邮件促销活动的客户的匿名标识。 </td> 
   <td colname="col4"> <p><b>状态</b>：已启用 </p> <p><b>分配</b>：最近 </p> <p><b>过期时间</b>：“业务决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已发送 </td> 
   <td colname="col3"> 用于存储从 Selligent 发送的电子邮件数量。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已送达 </td> 
   <td colname="col3"> 用于存储已送达的电子邮件数量。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 查看 </td> 
   <td colname="col3"> 用于存储已查看的独特电子邮件数量。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 点击 </td> 
   <td colname="col3"> 用于存储任何电子邮件的点击次数。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已退回 </td> 
   <td colname="col3"> 用于存储已退回的电子邮件数量。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Selligent 先决条件{#prerequisites-for-selligent}

列出在部署集成之前必须从您的 Selligent 帐户提供的信息。

**有效的 Selligent 帐户**

要使用此 Data Connectors 集成，您必须拥有有效的 Selligent 帐户。

**帐户信息**

在此集成设置过程中，您需要提供关于自己 Selligent 帐户的以下信息：

* **Adobe 服务 URL**：

   该 URL 可以从用于登录到 Selligent 营销解决方案的 URL 派生。将 URL 的“/simweb/login.aspx”部分替换为“/automation/omniture.asmx”

   例如：`http://<client-specific install url>/automation/omniture.asmx`

* **查询字符串参数：**&#x200B;消息 ID 和收件人 ID（访客 ID）的这些参数会附加到登陆页面 URL 中。对于消息 ID 和收件人 ID，这些参数始终分别为 MID 和 RID。

* **集成令牌：**&#x200B;从 Simweb 中启动管理器工具，然后转到&#x200B;**[!UICONTROL 配置]** > **[!UICONTROL 系统设置]** > **[!UICONTROL 常规]**&#x200B;选项卡 > **[!UICONTROL 系统]**。在&#x200B;**[!UICONTROL 安全性]**&#x200B;下，您可以找到集成令牌。

   ![](assets/selligent-integration_token.png)
