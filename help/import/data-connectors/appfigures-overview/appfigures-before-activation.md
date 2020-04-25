---
description: 在激活此集成之前，请针对您的 Adobe Analytics® 部署和电子邮件软件查看以下项目。
title: 在激活此集成之前
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 在激活此集成之前 {#before-you-activate-this-integration}

在激活此集成之前，请针对您的 Adobe Analytics® 部署和电子邮件软件查看以下项目。

这样做可确保在激活之前，遵循相应的最佳实践并满足相关先决条件，从而成功实现最佳集成。

## Adobe Analytics 要求{#adobe-analytics-requirements}

查看关于此 Data Connectors 集成的以下信息，这些信息与 Adobe Analytics 相关：

* **特定于报表包：**&#x200B;请注意，此集成特定于报表包。在激活集成之前，请确保已选择所需的报表包，并且该报表包中包含数据。
* **已配置的可用 Adobe Analytics 变量：**&#x200B;此集成需要 10 个自定义事件和 1 个自定义 eVar。请参阅 [Analytics 集成变量](appfigures-before-activation.md#analytics-integration-variables)。

* **使用实时数据初始化的报表包：**&#x200B;如果要为此集成创建全新的报表包，需要已经通过实时跟踪 appFigures 要求收到了一些（至少一次点击）数据。如果尚未记录实时数据，则报表包将无法接收集成的应用商店数据。

* **与应用商店的现有集成：**&#x200B;此集成会回填 13 个月的数据。为避免与您之前可能拥有的任何应用商店数据提供商发生任何重叠，请联系您的 appFigures 代表。告知他们您上次收到数据的日期。appFigures 会相应地调整回填期。

## appFigures 要求{#appfigures-requirements}

查看关于此 Data Connectors 集成的以下信息，这些信息与 appFigures 相关：

* **appFigures 的当前客户：**&#x200B;此集成要求您同时是 Adobe 用户和 appFigures 用户。如果您当前不是 appFigures 企业计划用户，则不具备完成集成向导所需的信息。有关更多信息，请访问 Web 上的 appFigures。
* **appFigures 帐户密钥：**&#x200B;需要 appFigures 帐户密钥才能激活 appFigures Data Connector。此帐户密钥可在“加载项”部分生成。有关更多信息，请参阅[配置集成](../appfigures-overview/t-appfigures-integration.md)。

* **数据终止化**：每天同步过去 7 天的下载、销售和排名信息。7 天后，数据会被视为最终数据，且不再更新。

## 定价{#pricing}

此 Data Connectors 集成涉及一些您需要注意的定价事项。

以下部分包含更多信息：

### Adobe 定价注意事项 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

目前，激活此集成不收取任何费用。但是，由于数据源导入，您可能会看到服务器调用略有增加。

### appFigures 定价注意事项 {#section-c6afad08c34b43e3a7a3637eea3328c3}

目前，使用此集成不收取任何费用。此集成当前仅适用于企业客户。有关更多信息，请[联系 appFigures](https://appfigures.com/support/contact)。

## Analytics 集成变量{#analytics-integration-variables}

appFigures 的 Data Connectors 集成使用 Analytics 变量来跟踪不同的 appFigures 量度。

下表描述了为 appFigures 集成自动激活的 Analytics 变量。

### 必需变量 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE] 此集成使用专用变量来获取应用商店数据，因此，您无需分配自定义商务变量和事件。

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| eVar | 应用商店对象 ID | 从 appFigures 导入。 | 使用“访问过期”、“最近分配”以及基本子关系来配置此 eVar。 |
| 事件（数字） | 应用商店下载 | 从 appFigures 导入。 | 移动应用程序下载次数。 |
| 事件（数字） | 应用商店购买（应用程序内） | 从 appFigures 导入。 | 应用程序内购买和订阅的次数。 |
| 事件（数字） | 应用商店排名 | 从 appFigures 导入。 | 用于定义平均 appFigures 计算量度。不直接使用。 |
| 事件（数字） | 应用商店排名因素 | 从 appFigures 导入。 | 用于定义平均 appFigures 计算量度。不直接使用。 |
| 事件（数字） | 应用商店评分 | 从 appFigures 导入。 | 用于定义平均 appFigures 计算量度。不直接使用。 |
| 事件（数字） | 应用商店评分因素 | 从 appFigures 导入。 | 用于定义平均 appFigures 计算量度。不直接使用。 |
| 事件（货币） | 应用商店收入（应用程序内） | 从 appFigures 导入。 | 应用程序内收入减去商店费用得到的金额。 |
| 事件（货币） | 应用商店收入（一次性） | 从 appFigures 导入。 | 应用程序购买金额减去商店费用得到的总收入。 |
| 事件（货币） | 应用商店版税（应用程序内） | 从 appFigures 导入。 | 不使用 |
| 事件（货币） | 应用商店版税（一次性） | 从 appFigures 导入。 | 不使用 |
