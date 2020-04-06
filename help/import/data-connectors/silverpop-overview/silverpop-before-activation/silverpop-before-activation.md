---
description: 在激活此集成之前，请针对您的 Adobe Analytics® 部署和电子邮件软件查看以下项目。
title: 在激活此集成之前
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 在激活此集成之前{#before-you-activate-this-integration}

在激活此集成之前，请针对您的 Adobe Analytics® 部署和电子邮件软件查看以下项目。

这样做可确保在激活之前，遵循相应的最佳实践并满足相关先决条件，从而成功实现最佳集成。

## Adobe Analytics{#adobe-analytics}

查看关于此 Data Connectors 集成的以下信息，这些信息与 Adobe Analytics 相关：

* **特定于报表包：**&#x200B;请注意，此集成特定于报表包。在激活集成之前，请确保已选择所需的报表包。
* **已配置的可用 Analytics 变量：**&#x200B;此集成需要 5 个自定义事件和 2 个自定义 eVar，以及可选的 3 个其他事件和 3 个其他 eVar。请参阅 [Analytics 集成变量](/help/import/data-connectors/silverpop-overview/silverpop-variables.md)。

* **授权代表：**&#x200B;请注意，根据您与 Adobe, Inc. 的服务协议或您与 Adobe 信任的某一合作伙伴的服务协议（如果适用），启用此集成可能会导致向贵公司收取相关费用。激活此集成，即表示您是贵公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **Data Warehouse™：**&#x200B;此集成要求启用 Data Warehouse 以生成再营销区段。如果尚未启用 Data Warehouse，请联系 Adobe 以了解详细信息。
* **收件人 ID：**&#x200B;此集成要求我们捕获“访客 ID”并将其存储在一个 Analytics 变量 (eVar) 中。访客 ID（通常称为“收件人 ID”）是 Silverpop 系统中电子邮件地址的编码或数字表示形式。此“收件人 ID”与提取到 Silverpop 系统中的网站下游访客行为（放弃购买、购买等）相关联，且可用于再营销。在设置过程中，当收到向导提示时，您必须为此确定一个 eVar。
* **外部跟踪：**&#x200B;如果您当前没有遵循为您发送的每个电子邮件促销活动启用外部跟踪这一最佳实践，则必须这样做以确保成功集成。有关详细信息，请参阅下面的 Silverpop 部分。
* **隐私合规：**&#x200B;您应该了解，启用“收件人 ID”或“访客 ID”跟踪功能，即表示该功能可能会跟踪您网站访客的个人身份信息。这会涉及隐私问题，需要贵组织实施适当的规程，例如，向网站访客发出通知并征得其同意。

## Silverpop Data Connector 集成{#silverpop-data-connector-integration}

查看关于此 Data Connector 集成的以下信息，这些信息与 Silverpop 相关：

* **有效的 Silverpop 帐户：**&#x200B;要使用此 Data Connectors 电子邮件集成，客户必须拥有启用电子邮件的活动 Silverpop 帐户以及活动用户凭据。
* **联系您的 Silverpop 代表**。此集成不会由 Silverpop 自动启用。在从 Analytics 导入或导出数据之前，必须联系 Silverpop 代表以启动 Silverpop 设置。

>[!NOTE] 此集成仅适用于 Engage（而非 Transact）组织。

## 定价{#pricing}

此 Data Connectors 集成涉及一些在激活之前您需要注意的定价事项。

### Adobe 定价注意事项 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

可能会产生与此集成相关的经常性费用和实施费用。有关定价详细信息，请联系您的 Adobe 客户代表。

### 合作伙伴定价注意事项 {#section-c6afad08c34b43e3a7a3637eea3328c3}

使用此集成可能会收取费用。有关定价信息，请联系您的客户关系经理。
