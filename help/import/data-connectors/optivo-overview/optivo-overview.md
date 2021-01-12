---
description: 此集成将电子邮件营销软件的集成式反馈系统与 Adobe Analytics 的行为报表整合在一起，为贵组织提供强大的分析和优化契机。
title: 适用于 Adobe Analytics 的 optivo® broadmail Data Connector
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 98%

---


# 适用于 Adobe Analytics 的 optivo® broadmail Data Connector{#optivo-broadmail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我们将于2021年8月1日终止Adobe数据连接器技术。 [了解更多...](/help/import/data-connectors/data-connectors-eol.md)

此集成将电子邮件营销软件的集成式反馈系统与 Adobe Analytics 的行为报表整合在一起，为贵组织提供强大的分析和优化契机。

[!DNL ~Partner~] 是一款专业的电子邮件营销软件。其主要功能是创建、发送和评估新闻通讯以及电子邮件促销活动。`[~Partner~]` 可作为云服务使用（软件即服务）。

`[~Partner~]` 集成提供了自动化的再营销和数据同步，从而提高转化率和收入。此集成让营销人员能够根据客户的电子邮件交互和网站行为，自动同步客户区段。可自定义区段的自动数据交换有助于创建极具针对性的电子邮件促销活动以提升销售额，例如，在放弃购买和结束购买后，通过再营销来实现产品的交叉销售、追加销售和二次销售。

此集成还会与 Adobe Analytics 交换 `[~Partner~]` 中的成功电子邮件促销活动量度。关键数据会集中显示在电子邮件促销活动概览中。

## Data Connectors 实验室计划 {#section-51f9864851b64d96873127b9ac9c9a2b}

此计划是 Adobe 第三方平台合作伙伴用于构建集成并将其交付到我们的联合市场的快速跟踪方法。这些集成完全由我们的合作伙伴开发，并按照社区方法在 Adobe Experience Cloud 上提供。Adobe Analytics 和其他解决方案的 Adobe 客户可获得这些集成，无需支付额外费用；同时，由于这些集成是第三方集成，因此它们将按原样提供，Adobe 不提供任何默示担保。

如果您对当前服务、被担保人或许可有任何疑问，请联系您的 Adobe 客户经理。

## 主要优势和功能{#key-benefits-and-features}

此集成具有以下主要优势：

* 挽回浏览并放弃的购物者
* 通过有针对性的交叉销售和追加销售再营销，提升销售额
* 基于区段的自动化促销活动
* 优化正在进行的促销活动
* [!DNL ~Partner~] 中的区段可实现有针对性的再营销
* 持续更新促销活动量度
* 自动化对话触发器

## 动态营销区段{#dynamic-marketing-segments}

此集成具有以下动态营销区段：

* **购买配置文件：**&#x200B;通过按访客购买模式定位的促销活动，增加重复订单和提高平均订单价值。
* **产品/内容查看行为配置文件：**&#x200B;通过基于产品查看和内容访问分析的营销区段，吸引潜在客户。
* **放弃购买配置文件：**&#x200B;通过专门针对那些犹豫是否要完成购物的访客而设计的优化促销活动，帮助将这些访客转化为客户。
* **有效的再营销：**&#x200B;客户还可以专门针对其用户需求创建和计划自定义再营销区段。

## 激活前{#before-you-activate}

在启动 Data Connectors 集成之前，请完成以下要求：

## Adobe Analytics 要求 {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **特定于报表包：**&#x200B;请注意，此集成特定于报表包。在激活集成之前，请确保已选择所需的报表包。
* **已配置的可用 Adobe Analytics 变量：**&#x200B;此集成需要自定义事件和自定义 eVar。

* **授权代表：**&#x200B;请注意，根据您与 Adobe, Inc. 的服务协议或您与 Adobe 信任的某一合作伙伴的服务协议（如果适用），启用此集成可能会导致向贵公司收取相关费用。激活此集成，即表示您是贵公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **消息 ID：**&#x200B;此集成要求我们捕获“消息 ID”并将其存储在一个 Adobe Analytics 变量 (eVar) 中。需要这些 ID 来标识您已发送的邮件。在设置过程中，当收到向导提示时，您必须为此确定一个 eVar。
* **Partner：**&#x200B;此集成要求我们捕获“[!UICONTROL ~Partner~]”并将其存储在一个 Adobe Analytics 变量 (eVar) 中。此 ID 是 [!UICONTROL ~Partner~] 系统中电子邮件地址的编码或数字表示形式。此“[!UICONTROL ~Partner~]”与提取到 [!UICONTROL ~Partner~] 系统中的网站下游访客行为（放弃购买、购买等）相关联，且可用于再营销。在设置过程中，当收到向导提示时，您必须为此确定一个 eVar。
* **点击后时间：**&#x200B;在设置过程中，此集成要求对点击后操作时间所对应的 eVar 进行赋值。在收件人单击邮件中的链接后，将关于收件人操作的信息传输到 [!UICONTROL ~Partner~] 时需要此信息。

* **点击后产品：**&#x200B;在设置过程中，此集成要求对提供的与点击后操作相关联的产品所对应的 eVar 进行赋值。在收件人单击邮件中的链接后，将关于收件人操作的信息传输到 [!UICONTROL ~Partner~] 时需要此信息。

* **点击后操作类型：**&#x200B;在设置过程中，此集成要求对点击后操作类型所对应的 eVar 进行赋值。在收件人单击邮件中的链接后，将关于收件人操作的信息传输到 [!UICONTROL ~Partner~] 时需要此信息。

* **隐私合规：**&#x200B;您应该了解，启用“收件人 ID”或“访客 ID”跟踪功能，即表示该功能可能会跟踪您网站访客的个人身份信息。这会涉及隐私问题，需要贵组织实施适当的规程，例如，向网站访客发出通知并征得其同意。

## 定价{#pricing}

请注意，根据您与 Adobe, Inc. 的服务协议或您与 Adobe 信任的某一合作伙伴的服务协议（如果适用），启用此集成可能会导致向贵公司收取相关费用。

激活此集成，即表示您是贵公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。

### Adobe 定价注意事项 {#section-1f4f46c0d969435db57d38c1c310a05a}

Adobe Analytics 解决方案的当前客户使用此 Data Connectors 集成无需支付额外费用。对于尚未迁移到新 Adobe Analytics 产品的客户，请联系 Adobe 客户代表以获取更多详细信息。

### 合作伙伴定价注意事项 {#section-f8ca71df32224412a5101efb6e356529}

此集成可供 [!DNL ~Partner~] 客户使用，但需要支付额外的集成费用。有关定价详细信息，请联系 sales@optivo.com。有关定价详细信息，请联系 [!DNL ~Partner~]。

## Adobe Analytics 变量{#adobe-analytics-variables}

此集成需要 Adobe Analytics 变量才能跟踪量度。

在确定要与此集成一起使用的事件和 eVar 后，必须在 Analytics Admin Console 中启用它们（有关说明，请参阅[报表包](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/manage-report-suites/report-suites-admin.html)）。
