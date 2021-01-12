---
description: 此 Adobe® Data Connectors 电子邮件集成将 Adobe Analytics® 中的行为信息与 Datran 电子邮件营销整合在一起，创建出一款功能强大的工具，通过更相关的消息传送来重新定义成功衡量指标和目标受众。
title: 适用于 Adobe Analytics 的 Datran Data Connector
uuid: f97655c4-9623-4d06-a3c6-894246eba80f
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 98%

---


# 适用于 Adobe Analytics 的 Datran Data Connector {#datran-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我们将于2021年8月1日终止Adobe数据连接器技术。 [了解更多...](/help/import/data-connectors/data-connectors-eol.md)

此 Adobe® Data Connectors 电子邮件集成将 Adobe Analytics® 中的行为信息与 Datran 电子邮件营销整合在一起，创建出一款功能强大的工具，通过更相关的消息传送来重新定义成功衡量指标和目标受众。

向这些市场区段发送相关电子邮件，可能会带来全新的收入契机，从而在新电子邮件促销活动和现有电子邮件促销活动中提高转化率和收入。例如，经证实，根据访问期间查看的产品或放弃购买的产品发送相关电子邮件，可对收入产生显著影响，并且对成本的影响最小，因为这只是利用网站已获取的访客。提高营销效率，是 Adobe Analytics 与 Datran 集成的主要优势之一。此外，此集成会自动将电子邮件量度与 Adobe Analytics 数据同步（频率为每小时一次），以实现闭环报告。

## 主要优势{#key-benefits}

此集成具有以下主要优势：

* 将电子邮件营销数据与 Analytics 数据整合到一个报表界面中
* 通过转化为收入和促进网站取得成功，优化电子邮件促销活动
* 根据动态营销区段，向关键访客和市场区段进行再营销

## 动态营销区段{#dynamic-marketing-segments}

此 Data Connectors 电子邮件集成支持动态营销区段，以帮助您推动业务发展。

此集成具有以下开箱即用的营销区段：

* **购买配置文件：**&#x200B;通过按访客购买模式定位的促销活动，增加重复订单和提高平均订单价值。
* **产品/内容查看行为配置文件：**&#x200B;通过基于产品查看和内容访问分析的营销区段，吸引潜在客户。
* **放弃购买配置文件：**&#x200B;通过专门针对那些犹豫是否要完成购物的访客而设计的优化促销活动，帮助将这些访客转化为客户。
* 客户还可以专门针对其用户需求创建和计划自定义再营销区段。

## 集成过程和先决条件{#integration-procedure-and-prerequisites}

使用“即插即用”向导，直观的分步流程将引导您完成各个系统同步点并初始化集成。

此 Data Connectors 集成需要满足以下条件：

### Adobe 先决条件 {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Data Warehouse
* Adobe Analytics 帐户
* 已配置的可用 Adobe Analytics 变量，包括 eVar 和自定义事件。

### Datran 先决条件 {#section-bcb904574ccf42308bcf7a15e45b4d58}

* 启用了电子邮件的有效 StormPost 帐户，以及有效的用户凭据。

查看关于此 Data Connectors 集成的以下信息，这些信息与 Datran 相关：

* **有效的 Datran 帐户：**&#x200B;要使用此 Data Connectors 电子邮件集成，客户必须拥有有效的 Datran 帐户。
* **Datran 的当前客户：**&#x200B;此集成要求您同时是 Adobe 客户和 Datran 客户。如果您当前不是 Datran 客户，则不具备完成集成向导所需的信息。如果您当前是 Datran 客户，则需要您的 Datran 帐户 ID 或分配给贵组织的唯一标识符，才能完成集成向导。
* 有关 StormPost 设置说明，请联系您的客户经理。

## 定价{#pricing}

此 Data Connectors 集成涉及一些您需要注意的定价事项。

以下部分包含更多信息：

### Adobe 定价注意事项 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

可能会产生与此集成相关的经常性费用和实施费用。有关定价详细信息，请联系您的 Adobe 客户代表。

### Datran 定价注意事项 {#section-c6afad08c34b43e3a7a3637eea3328c3}

使用此集成可能会收取费用。

* 有关定价信息，请通过发送电子邮件 (esp@datranmedia.com) 联系我们。

## 激活此集成之前的须知事项{#what-you-should-know-before-activating-this-integration}

在激活此集成之前，请针对您的 Adobe Analytics® 部署和电子邮件软件查看以下项目。

这样做可确保在激活之前，遵循相应的最佳实践并满足相关先决条件，从而成功实现最佳集成。

### Adobe Analytics{#adobe-analytics}

查看关于此 Data Connectors 集成的以下信息，这些信息与 Adobe Analytics 相关：

* **特定于报表包：**&#x200B;请注意，此集成特定于报表包。在激活集成之前，请确保已选择所需的报表包。
* **授权代表：**&#x200B;请注意，根据您与 Adobe, Inc. 的服务协议或您与 Adobe 信任的某一合作伙伴的服务协议（如果适用），启用此集成可能会导致向贵公司收取相关费用。激活此集成，即表示您是贵公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **Omniture Data Warehouse™：**&#x200B;此集成要求启用 Data Warehouse 以生成再营销区段。如果尚未启用 Data Warehouse，请联系 Adobe 以了解详细信息。
* **收件人 ID：**&#x200B;此集成要求我们捕获“访客 ID”并将其存储在一个 Adobe Analytics 变量 (eVar) 中。访客 ID（通常称为“收件人 ID”）是 Datran 系统中电子邮件地址的编码或数字表示形式。此“收件人 ID”与提取到 Datran 系统中的网站下游访客行为（放弃购买、购买等）相关联，且可用于再营销。在设置过程中，当收到向导提示时，您必须为此确定一个 eVar。
* **外部跟踪：**&#x200B;如果您当前没有遵循为您发送的每个电子邮件促销活动启用外部跟踪这一最佳实践，则必须这样做以确保成功集成。有关详细信息，请参阅下面的 Datran 部分。
* **隐私合规：**&#x200B;您应该了解，启用“收件人 ID”或“访客 ID”跟踪功能，即表示该功能可能会跟踪您网站访客的个人身份信息。这会涉及隐私问题，需要贵组织实施适当的规程，例如，向网站访客发出通知并征得其同意。
