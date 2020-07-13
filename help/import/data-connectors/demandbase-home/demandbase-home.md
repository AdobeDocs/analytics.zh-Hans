---
description: 'null'
title: 适用于 Adobe Analytics 的 Demandbase Data Connector
uuid: 28fddb8f-06f6-4447-8257-4a59131bedbe
translation-type: tm+mt
source-git-commit: 0fed9fd179feadae26a364a2ca79ac396251e8f6
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 96%

---


# 适用于 Adobe Analytics 的 Demandbase Data Connector{#demandbase-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我们将在2021年中后期终止Adobe Data Connector技术。 [了解更多...](/help/import/data-connectors/data-connectors-eol.md)

此 Adobe® Data Connectors 集成将 Demandbase 的实时 ID 服务与 Adobe Analytics 中的行为信息整合在一起，为 B2B 组织创造强大的分析、优化和内容个性化契机。

通过根据预先确定的特性向潜在客户提供相关内容，发掘更多合适的商机并提高转化率。通过提供与特定行业、公司规模甚至特定公司本身相关的内容，使您能够直接向访客提供正确的信息，而无需他们在您的网站上自行查找。这将减少跳出次数，并提供一个更有序、更合格的转化漏斗。

## 主要优势和功能{#key-benefits-and-features}

列出 5 大优势和功能。

* 提供关于 8 个标准 Demandbase 组织维度（如公司名称、行业和收入范围）的流量和转化报表。
* 允许您额外包含 8 个可选的 Demandbase 维度。这些维度可以包括“帐户监视”维度。
* 能够使用 Demandbase 维度在 Adobe Experience Cloud 中构建和应用区段。
* 提供报表包变量优化。只需使用 2 个自定义转化变量 (eVar)，即可捕获所有 16 个可能的 Demandbase 维度。
* 允许您将集成的 Demandbase 维度发送到 Adobe Target，以便用于定位特定受众。

## 集成先决条件{#integration-prerequisites}

列出 Adobe 客户和 Demandbase 客户的先决条件。

### Adobe 客户先决条件 {#section-ce8963ca1c1741009d842222c6a49063}

* 必须是 Adobe Analytics 的当前客户。
* 必须是 Adobe Experience Cloud 管理员用户，且有权启用 Data Connectors。
* 您的报表包中必须至少具有 1 个已启用的可用 eVar 变量。第二个 eVar 是可选的。

### Demandbase 客户先决条件 {#section-08e14afe216a4b0db9e7e2965894de6f}

* 必须是 Demandbase 的当前客户。
* 必须具有有效且获得 Analytics 许可的 Demandbase API 密钥。
* **可选：**&#x200B;必须具有有效且获得内容个性化许可的 Demandbase API 密钥。仅当您打算在 Adobe Target 中激活集成的 Demandbase 维度时，才需具有该密钥。
