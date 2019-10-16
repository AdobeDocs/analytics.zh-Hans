---
description: 本文档描述了您在Adobe Analytics中需要执行哪些操作来支持数据主体的CCPA访问和删除权限。
seo-description: 本文档描述了您在Adobe Analytics中需要执行哪些操作来支持数据主体的CCPA访问和删除权限。
seo-title: Adobe Analytics和CCPA
title: Adobe Analytics和CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---


# Adobe Analytics和CCPA

本文档描述了您在Adobe Analytics中需要执行哪些操作来支持数据主体的CCPA访问和删除权限。

## Adobe 概述

>[!IMPORTANT]本文档的内容不是法律建议，也不会代替法律建议。有关CCPA的建议，请咨询贵公司的法务部门。

2020年1月1日，加利福尼亚州消费者隐私法(CCPA)生效。 For more information about Adobe's response and what this means for you as an Adobe customer, see [Adobe's Privacy Center.](https://www.adobe.com/privacy.html)

Adobe 向企业提供软件和服务时，作为提供服务的一部分，Adobe 将以数据处理者身份，代表我们的客户对收到和存储的任何个人数据进行处理。作为数据处理者，Adobe会根据贵公司的许可和指示（例如，您与Adobe的协议中所述）处理个人数据。

作为数据管理者，您需要确定Adobe代表您处理和存储的个人数据。 如果您使用 Adobe Experience Cloud 解决方案，Adobe 可能会根据您使用的解决方案和您选择发送到 Adobe Experience Cloud 帐户的信息来为您托管个人数据。For a list of examples, see [Adobe Experience Cloud privacy.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## Adobe如何处理CCPA数据

Adobe Cloud Platform (ACP) 提供了一项集成的解决方案，它将您的品牌的数据管理基础架构与它用来创建和管理客户体验的 Adobe 工具结合在一起。Adobe Cloud Platform 的数据管理功能可以将数据管理策略与数据的使用直接关联到一起。

Familiarize yourself with [how Adobe Analytics handles GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) which discusses steps for privacy readiness and how to integrate with the Adobe Experience Cloud Privacy Service API.

## CCPA就绪性和您的Adobe Analytics数据

Adobe 认识到您最熟悉您的报表包中的自定义数据，因此我们将为您提供机会来定义数据管理设置和首选项。To that end, Adobe Analytics provides a Data Governance user interface that lets you, as the data controller, set [privacy labels](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) on your Analytics report suites and all the dimensions and metrics in those report suites. 您可以标识数据集中包含直接可识别数据或间接可识别数据的列，以便能够提交访问和删除请求来处理这些数据。对于每个请求，在 Analytics“数据管理”用户界面中定义的标签将用于对应该请求的特定标识符。

请参阅[为报表包数据设置标签](/help//admin/c-data-governance/gdpr-setup-reportsuite.md)，以了解有关如何设置标签的更多信息。

## 先决条件

* Familiarize yourself with [GDPR terminology.](/help/admin/c-data-governance/gdpr-terminology.md)
* 将您的登录公司关联到 Experience Cloud 组织（如果尚未关联）。Contact Adobe Customer Care and refer to [Organizations and account linking.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Map any Adobe Analytics report suite that you want to set up for data governance to [your Experience Cloud organization.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* 为每个报告套件设置数据保留策略，以便接受CCPA删除和访问请求。

   Adobe Analytics无法帮助您处理对Privacy Services API的请求，即处理您从最终用户收到的访问或删除请求（如果Adobe Analytics中未设置数据保留期）。 请联系您的客户成功经理以便设置数据保留期限。

* 检查您的权限：要在 Adobe Analytics 中使用“数据管理”管理界面，您必须是 Adobe Analytics 管理员。
* 考虑实施同意 [管理变量](/help/admin/c-data-governance/consent-variables.md) ，以跟踪点击级别的同意状态。
