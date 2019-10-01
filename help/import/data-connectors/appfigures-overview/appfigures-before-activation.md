---
description: 在激活此集成之前，请根据您的Adobe Analytics®部署和电子邮件软件检查以下项目。
seo-description: 在激活此集成之前，请根据您的Adobe Analytics®部署和电子邮件软件检查以下项目。
seo-title: 在激活此集成之前
title: 在激活此集成之前
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# 在激活此集成之前 {#before-you-activate-this-integration}

在激活此集成之前，请根据您的Adobe Analytics®部署和电子邮件软件检查以下项目。

这样做将确保在激活之前有适当的最佳实践或先决条件，这将导致最佳和成功的集成。

## Adobe Analytics Requirements{#adobe-analytics-requirements}

查看与Adobe Analytics相关的有关此数据连接器集成的以下信息：

* **** 特定于报表包：请注意，此集成特定于报表包。 请确保在激活集成之前已选择所需的报表包，并且报表包包含数据。
* **** 可用和配置的Analytics变量：此集成需要10个自定义事件和1个自定义eVar。 请参阅 [分析集成变量](appfigures-before-activation.md#analytics-integration-variables)。

* **** 使用实时数据初始化的报表包：如果要为此集成创建全新的报表包，它需要通过实时跟踪appFigures要求接收一些（至少一次点击）数据。 如果尚未记录实时数据，则报表包将无法接收集成的App store数据。

* **** 与App Store的现有集成：此集成可回填13个月的数据。 为避免与您之前可能拥有的任何App Store数据提供商发生任何重叠，请联系您的appFigures代表。 让他们知道您上次收到数据的日期。 appFigures将相应地调整回填期。

## appFigures Requirements{#appfigures-requirements}

查看与appFigures相关的有关此数据连接器集成的以下信息：

* **** appFigures的当前客户：此集成要求您同时是Adobe和appFigures的用户。 如果您当前不是appFigures企业计划的用户，您将没有完成集成向导所需的信息。 请访问Web上的appFigures以了解更多信息。
* **** appFigures帐户密钥：需要appFigures帐户密钥才能激活appFigures数据连接器。 此帐户密钥可在“Add-ons”部分生成。 有关详细 [信息，请参阅](../appfigures-overview/t-appfigures-integration.md) “配置集成”。

* **数据终止化**:下载、销售和排名信息在前7天内每天都会同步。 7天后，数据将视为最终数据，并且不再更新。

## 定价{#pricing}

此数据连接器集成包括您需要注意的定价注意事项。

以下部分包含更多信息：

### Adobe定价注意事项 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

目前，激活此集成不收取任何费用。 但是，由于数据源导入，您可能会看到服务器调用略有增加。

### appFigures定价注意事项 {#section-c6afad08c34b43e3a7a3637eea3328c3}

目前没有与此集成相关的费用。 此集成目前仅对Enterprise客户可用。 请联 [系appFigures](https://appfigures.com/support/contact) ，了解更多信息。

## Analytics Integration Variables{#analytics-integration-variables}

appFigures的数据连接器集成使用Analytics变量跟踪各种appFigures指标。

下表介绍了为appFigures集成自动激活的Analytics变量。

### 必需变量 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>此集成使用专用变量来获取应用商店数据，因此您无需分配自定义商务变量和事件。

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| eVar | 应用商店对象 ID | 从appFigures导入。 | 配置此eVar，其访问到期、最近分配和基本子关系。 |
| event（数字） | 应用商店下载 | 从appFigures导入。 | 移动应用程序下载次数。 |
| event（数字） | App Store购买（应用程序内） | 从appFigures导入。 | 应用程序内购买和订阅的数量。 |
| event（数字） | 应用商店排名 | 从appFigures导入。 | 用于定义平均appFigures计算量度。 不直接使用。 |
| event（数字） | 应用商店排名因素 | 从appFigures导入。 | 用于定义平均appFigures计算量度。 不直接使用。 |
| event（数字） | App Store 排行榜 | 从appFigures导入。 | 用于定义平均appFigures计算量度。 不直接使用。 |
| event（数字） | App Store 排名因素 | 从appFigures导入。 | 用于定义平均appFigures计算量度。 不直接使用。 |
| event(currency) | App Store收入（应用程序内） | 从appFigures导入。 | 应用程序内收入减去商店费用。 |
| event(currency) | App Store收入（一次性） | 从appFigures导入。 | 来自应用购买的总收入减去商店费用。 |
| event(currency) | App Store版税（应用程序内） | 从appFigures导入。 | 未使用 |
| event(currency) | App Store版税（一次性） | 从appFigures导入。 | 未使用 |
