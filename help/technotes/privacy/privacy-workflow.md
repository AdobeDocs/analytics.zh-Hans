---
description: 概述您可以采取哪些步骤来启用 Adobe Analytics 实施，以便支持数据主体的数据隐私访问和删除权利。
title: 隐私工作流程
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
TQID: 'https://experienceleague.adobe.com/n0zqbcuPD2lvtgYNtdQx5VsBl-FrmzfqU-z2iIn83hg'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 59%

---

# 隐私工作流程

此工作流程概述您需要采取哪些步骤来准备 Adobe Analytics 实施，以便支持数据主体的数据隐私访问和删除权利。

1. 从 Adobe Experience Platform 中的 [Privacy Service 概述](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)页面开始，了解在为 Analytics 数据赋予标签之前要问哪些问题。
1. **设置您的数据保留策略。** Adobe需要数据保留策略来处理数据隐私数据访问/删除请求。  有关更多信息，请参阅[数据保留常见问题解答](/help/technotes/data-retention.md)。 为了使用 Privacy Service API，您必须确保在 Adobe Analytics 中设置数据保留期。
1. **熟悉数据隐私标签、Adobe Analytics ID和命名空间。** 查看[Analytics变量的数据隐私标签](/help/admin/tools/privacy-labeling/labels.md)和[标签设置最佳实践](/help/admin/tools/privacy-labeling/best-practices.md)。
1. **向报表包中的每个变量分配身份、敏感性和数据管理标签。** 每次创建新报表包或在现有报表包中启用新变量时，都需要对标签设置进行审核。 此外，在启用新的解决方案集成时也需要审核标签设置，因为这些集成会公开可能要求设置标签的新变量。 重新实施您的移动应用程序或网站时，可能会改变现有变量的使用方式，这或许也需要更新标签。 请参阅[为报告包数据设置标签](/help/admin/tools/privacy-labeling/namespaces.md)。
1. **连接到Adobe数据隐私API并提交访问和删除请求。** 作为Adobe Analytics客户，您可以通过调用[Adobe Experience Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans)，提交单独的数据隐私请求以访问和删除客户数据。 您可以在请求中提交任何 Analytics 标识符（如[标签设置最佳实践](/help/admin/tools/privacy-labeling/best-practices.md)一节中所述）及其各自的命名空间 ID（数据源 ID）。
1. **查看并管理报表包的数据隐私设置。** 查看[查看报表包的数据管理设置](/help/admin/tools/privacy-labeling/view-settings.md)。
