---
description: 此Adobe® Data Connectors电子邮件集成将Adobe Analytics®的行为信息与Datran电子邮件营销相结合，创建出一个功能强大的工具，用于重新定义成功衡量并通过更相关的消息定位受众。
title: Adobe Analytics的Data Connector
uuid: f97655c4-9623-4d06-a3c6-894246eba80f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Datran Data Connector for Adobe Analytics {#datran-data-connector-for-adobe-analytics}

此Adobe® Data Connectors电子邮件集成将Adobe Analytics®的行为信息与Datran电子邮件营销相结合，创建出一个功能强大的工具，用于重新定义成功衡量并通过更相关的消息定位受众。

向这些市场领域提供相关电子邮件可能会带来全新的收入机会，从而在新电子邮件和现有电子邮件营销活动中提高转化率和收入。 例如，根据访问期间查看的产品或放弃购物车中的产品发送相关电子邮件已证明对收入产生显着影响，并且对成本的影响最小，因为这只是利用您的网站已获得的访客。 营销效率的提高是将Adobe Analytics与Datran集成的主要优势之一。 此外，此集成将自动将电子邮件指标与Adobe Analytics数据同步，频率与闭环报告每小时相同。

## 主要优点{#key-benefits}

此集成包括以下主要优点：

* 将电子邮件营销和分析数据整合到一个报告界面中
* 通过转化率和对收入和网站成功贡献来优化电子邮件营销活动
* 根据动态营销细分，向关键访客和市场细分进行再营销

## 动态营销细分{#dynamic-marketing-segments}

此Data Connectors电子邮件集成支持动态营销细分，以帮助您推动业务发展。

此集成具有以下开箱即用的营销细分：

* **** 购买配置文件：通过按访客购买模式定向的营销活动增加重复订购和平均订单价值。
* **** 产品／内容查看行为配置文件：根据产品视图和内容访问情况分析，通过营销细分接触潜在客户。
* **** 购物车放弃资料：通过专门为犹豫是否完成购物车的客户设计的优化营销活动，帮助访客转化为客户。
* 客户还可以根据用户的需求创建和计划自定义再营销细分。

## 集成过程和先决条件{#integration-procedure-and-prerequisites}

使用“即插即用”向导，直观的分步进程将引导您完成系统同步点并初始化集成。

此数据连接器集成需要：

### Adobe先决条件 {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Data Warehouse
* Adobe Analytics帐户
* 可用和配置的Adobe Analytics变量，包括eVar和自定义事件。

### 数据库先决条件 {#section-bcb904574ccf42308bcf7a15e45b4d58}

* 启用了电子邮件的活动StormPost帐户和活动的用户凭据。

查看与Data Connectors相关的有关此Data Connectors集成的以下信息：

* **** 有效的数据帐户：要使用Data Connectors电子邮件集成，客户端必须具有有效的Datran帐户。
* **** 当前数据客户：此集成要求您同时是Adobe和Datran的客户。 如果您当前不是Datran的客户，您将没有完成集成向导所需的信息。 如果您当前是Datran的客户，则需要您的Datran帐户ID或分配给您的组织的唯一标识符，以完成集成向导。
* 有关StormPost设置说明，请与您的客户经理联系。

## 定价{#pricing}

此Data Connectors集成包括您需要注意的定价注意事项。

以下部分包含更多信息：

### Adobe定价注意事项 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

此集成可能需要反复支付和实施费用。 有关定价详细信息，请联系您的Adobe客户代表。

### 数据定价注意事项 {#section-c6afad08c34b43e3a7a3637eea3328c3}

此集成可能会收取相关费用。

* 请通过电子邮件联系我们，了解定价信息，网址为esp@datranmedia.com。

## 激活此集成前您应了解的内容{#what-you-should-know-before-activating-this-integration}

在激活此集成之前，请根据您的Adobe Analytics®部署和电子邮件软件检查以下项目。

这样做将确保在激活之前有适当的最佳实践或先决条件，这将导致最佳和成功的集成。

### Adobe Analytics{#adobe-analytics}

查看与Adobe Analytics相关的有关此Data Connectors集成的以下信息：

* **** 报表包特定：请注意，此集成是特定于报表包的。 在激活集成之前，请确保已选择所需的报表包。
* **** 委托代理人：请注意，启用此集成可能会导致贵公司根据您与Adobe, Inc.的服务协议或您与Adobe信任的合作伙伴之一的服务协议（如果适用）产生费用。 通过激活此集成，您即表示您是您公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **** Omniture Data Warehouse™:此集成要求启用数据仓库才能生成再营销区段。 如果尚未启用数据仓库，请与Adobe联系以了解详细信息。
* **** 收件人ID:该集成要求我们在Adobe Analytics变量(eVar)中捕获并存储“访客ID”。 访客ID（通常称为“收件人ID”）是Datran系统中电子邮件地址的编码或数字表示形式。 此“收件人ID”与网站上的下游访客行为（购物车放弃、购买等）相关联它被引入Datran系统，并可用于再营销目的。 在设置过程中，当向导提示时，您必须为此标识eVar。
* **** 外部跟踪：如果您当前没有遵循为您发送的每个电子邮件营销活动启用外部跟踪的最佳实践，则必须这样做以确保成功集成。 有关详细信息，请参阅下面的“数据”部分。
* **** 隐私合规性：您应该了解，通过启用“收件人”或“访客ID”跟踪功能，可跟踪网站访客的个人身份信息。 这涉及隐私问题，需要贵组织实施适当的程序，例如向网站访客发出通知并征得其同意。
