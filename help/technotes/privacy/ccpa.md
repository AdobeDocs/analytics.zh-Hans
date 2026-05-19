---
description: 本文档将介绍您需要在 Adobe Analytics 中执行什么操作来支持数据主体的 CCPA 访问和删除权限。
title: Adobe Analytics 和 CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
TQID: https://experienceleague.adobe.com/medgbA9EBG0fE2xttZ7HLKT42-RBr7rlMGGGGrAyoKw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 63%

---

# Adobe Analytics 和 CCPA

本文档将介绍您需要在 Adobe Analytics 中执行什么操作来支持数据主体的 CCPA 访问和删除权限。

## Adobe 概述

>[!IMPORTANT]
>
>本文档的内容不是法律建议，也不会代替法律建议。 请咨询贵公司的法律部门，以获取有关 CCPA 的建议。

《加州消费者隐私法案》(CCPA) 将于 2020 年 1 月 1 日正式生效。 有关 Adobe 对此作何回应以及它对 Adobe 客户有何影响的更多信息，请参阅 [Adobe 的隐私中心](https://www.adobe.com/cn/privacy.html)。

Adobe 向企业提供软件和服务时，作为提供服务的一部分，Adobe 将以数据处理者身份，代表我们的客户对收到和存储的任何个人数据进行处理。 作为“数据处理方”，Adobe 将根据贵公司授予的权限及指示（例如，遵照您与 Adobe 签署的协议中的规定）处理个人数据。

作为“数据控制者”，您可以决定 Adobe 代表您处理和存储的个人数据。 如果您使用Adobe CX Enterprise解决方案，Adobe可能会根据您使用的解决方案和您选择发送到Adobe CX Enterprise帐户的信息，来为您托管个人数据。 有关示例列表，请参阅[Adobe CX Enterprise隐私。](https://www.adobe.com/cn/privacy/marketing-cloud.html#collect)

## Adobe 如何处理 CCPA 数据

Adobe CX Enterprise提供了一个集成式解决方案，它将您品牌的数据治理基础架构与其用于创建和管理消费者体验的Adobe工具连接在一起。 Adobe CX Enterprise的数据管理功能实现了数据管理策略与数据使用的直接关联。

熟悉[Adobe Analytics如何处理GDPR](https://www.adobe.com/cn/data-analytics-cloud/analytics/general-data-protection-regulation.html)，其中讨论了做好隐私法准备工作的步骤，以及如何集成Adobe CX Enterprise Privacy Service API。

## CCPA 准备工作和您的 Adobe Analytics 数据

Adobe 认识到您最熟悉您的报告包中的自定义数据，因此我们将为您提供机会来定义数据管理设置和首选项。
为此，Adobe Analytics 提供了“数据管理”用户界面，允许您作为数据控制者，对您的 Analytics 报告包以及这些报告包中的所有维度和量度设置[隐私权标签](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels)。 您可以识别数据集中包含直接可识别数据或间接可识别数据的列，以便提交访问和删除请求以处理该数据。 对于每个请求，Analytics数据管理用户界面中定义的标签将被用于与该请求对应的特定标识符。

请参阅[为报告包数据设置标签](/help/admin/tools/privacy-labeling/labeling-overview.md)，以详细了解如何设置标签。
