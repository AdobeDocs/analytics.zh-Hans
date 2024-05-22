---
description: 本文档介绍您需要在 Adobe Analytics 中执行什么操作来支持数据主体的 GDPR 访问和删除权利。
title: Adobe Analytics 和 GDPR
feature: Data Governance
role: Admin
exl-id: 4cb19f63-119f-4853-84bf-5c1e8f9af9f0
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 87%

---

# Adobe Analytics 和 GDPR

本文档介绍您需要在 Adobe Analytics 中执行什么操作来支持数据主体的 GDPR 访问和删除权利。

## Adobe 概述 {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>本文档的内容不是法律建议，也不会代替法律建议。请咨询贵公司的法律部门，以获取有关 GDPR 的建议。

2018 年 5 月 25 日，欧盟的《通用数据保护条例》（GDPR，也译为“一般数据保护规定”）已正式生效。有关 Adobe 对此作何回应以及它对 Adobe 客户有何影响的更多信息，请参阅 [GDPR 与您的业务](https://www.adobe.com/cn/privacy/general-data-protection-regulation.html)。

Adobe 向企业提供软件和服务时，作为提供服务的一部分，Adobe 将以数据处理者身份，代表我们的客户对收到和存储的任何个人数据进行处理。作为“数据处理方”，Adobe 将根据贵公司授予的权限及指示（例如，遵照您与 Adobe 签署的协议中的规定）处理个人数据。

作为“数据控制者”，您可以决定 Adobe 代表您处理和存储的个人数据。如果您使用 Adobe Experience Cloud 解决方案，Adobe 可能会根据您使用的解决方案和您选择发送到 Adobe Experience Cloud 帐户的信息来为您托管个人数据。有关示例列表，请参阅 [Adobe Experience Cloud 隐私权。](https://www.adobe.com/cn/privacy/marketing-cloud.html#collect)

![](assets/privacy_ready.png)

## Adobe 如何处理 GDPR 数据 {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Experience Cloud提供了一个集成式解决方案，可将贵品牌的数据治理基础架构与其用于创建和管理消费者体验的Adobe工具连接起来。 Adobe Experience Cloud的数据治理功能可将数据治理策略与数据使用直接联系起来。

熟悉 [Adobe Analytic 如何处理 GDPR](https://www.adobe.com/cn/data-analytics-cloud/analytics/general-data-protection-regulation.html)，其中讨论了做好 GDPR 准备工作的步骤，以及如何集成 Adobe Experience Cloud GDPR API。

## GDPR 准备工作和您的 Adobe Analytics 数据 {#section_9A47CDCD614C42238F6E05CFF0180195}

Adobe 认识到您最熟悉您的报表包中的自定义数据，因此我们将为您提供机会来定义数据管理设置和首选项。

为此，Adobe Analytics 提供了“数据管理”用户界面，允许您作为数据控制者，对您的 Analytics 报表包以及这些报表包中的所有维度和量度设置[隐私权标签](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels)。您可以标识数据集中包含直接可识别数据或间接可识别数据的列，以便能够提交访问和删除请求来处理这些数据。对于每个请求，在 Analytics“数据管理”用户界面中定义的标签将用于对应该请求的特定标识符。

请参阅 [为报表包数据设置标签](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md) 有关如何设置标签的详细信息。

## 先决条件 {#section_3C766371CE0641C0821FE8E750E5AE0C}

* 熟悉 [GDPR 术语。](/help/admin/c-data-governance/gdpr-terminology.md)
* 将您的登录公司关联到 Experience Cloud 组织（如果尚未关联）。请联系 Adobe 客户关怀团队并参阅[组织和帐户关联。](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=zh-Hans)
* 为每个报表包设置一项数据保留策略，以便能够处理 GDPR 删除和访问请求。

  >[!NOTE]
  >
  >如果未在 Adobe Analytics 中设置数据保留期限，Adobe Analytics 将无法协助您处理 GDPR API 请求，例如，处理您从最终用户那里收到的访问请求或删除请求。请联系您的Adobe客户团队以设置数据保留期限。

* 检查您的权限：要在 Adobe Analytics 中使用“数据管理”管理界面，您必须是 Adobe Analytics 管理员。

