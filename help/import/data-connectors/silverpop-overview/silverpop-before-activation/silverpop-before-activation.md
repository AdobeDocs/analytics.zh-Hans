---
description: 在激活此集成之前，请根据您的Adobe Analytics®部署和电子邮件软件检查以下项目。
title: 在激活此集成之前
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 在激活此集成之前{#before-you-activate-this-integration}

在激活此集成之前，请根据您的Adobe Analytics®部署和电子邮件软件检查以下项目。

这样做将确保在激活之前有适当的最佳实践或先决条件，这将导致最佳和成功的集成。

## Adobe Analytics{#adobe-analytics}

查看与Adobe Analytics相关的有关此Data Connectors集成的以下信息：

* **** 报表包特定：请注意，此集成是特定于报表包的。 在激活集成之前，请确保已选择所需的报表包。
* **** 可用和配置的Analytics变量：此集成需要5个自定义事件和2个自定义eVar，以及（可选）3个附加事件和3个附加eVar。 请参阅 [分析集成变量](/help/import/data-connectors/silverpop-overview/silverpop-variables.md)。

* **** 委托代理人：请注意，启用此集成可能会导致贵公司根据您与Adobe, Inc.的服务协议或您与Adobe信任的合作伙伴之一的服务协议（如果适用）产生费用。 通过激活此集成，您即表示您是您公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **** Data Warehouse™:此集成要求启用数据仓库才能生成再营销区段。 如果尚未启用数据仓库，请与Adobe联系以了解详细信息。
* **** 收件人ID:该集成要求我们在Analytics变量(eVar)中捕获并存储“访客ID”。 访客ID（通常称为“收件人ID”）是Silverpop系统电子邮件地址的编码或数字表示形式。 此“收件人ID”与网站上的下游访客行为（购物车放弃、购买等）相关联被引入Silverpop系统，并可用于再营销目的。 在设置过程中，当向导提示时，您必须为此标识eVar。
* **** 外部跟踪：如果您当前没有遵循为您发送的每个电子邮件营销活动启用外部跟踪的最佳实践，则必须这样做以确保成功集成。 有关详细信息，请参阅下面的Silverpop部分。
* **** 隐私合规性：您应该了解，通过启用“收件人”或“访客ID”跟踪功能，可跟踪网站访客的个人身份信息。 这涉及隐私问题，需要贵组织实施适当的程序，例如向网站访客发出通知并征得其同意。

## Silverpop Data Connector集成{#silverpop-data-connector-integration}

查看与Silverpop相关的有关此Data Connector集成的以下信息：

* **** 有效的Silverpop帐户：要使用Data Connectors电子邮件集成，客户端必须具有启用电子邮件的活动Silverpop帐户和活动用户凭据。
* **联系您的Silverpop代表**。 此集成不会由Silverpop自动启用。 在从Analytics导入或导出数据之前，必须联系Silverpop代表以启动Silverpop设置。

> [!NOTE] 此集成仅适用于参与组织（而非交易）。

## 定价{#pricing}

此Data Connectors集成包括激活前需要考虑的定价注意事项。

### Adobe定价注意事项 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

此集成可能需要反复支付和实施费用。 有关定价详细信息，请联系您的Adobe客户代表。

### 合作伙伴定价注意事项 {#section-c6afad08c34b43e3a7a3637eea3328c3}

此集成可能会收取相关费用。 有关定价信息，请与您的关系经理联系。
