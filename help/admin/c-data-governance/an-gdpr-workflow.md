---
description: 概述您可以采取哪些步骤来启用 Adobe Analytics 实施，以便支持数据主体的数据隐私访问和删除权利。
title: 隐私工作流程
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 4bbed2efde0574bc9f5f6a78a022a22490e75549
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 81%

---

# 隐私工作流程

此工作流程概述您需要采取哪些步骤来准备 Adobe Analytics 实施，以便支持数据主体的数据隐私访问和删除权利。

1. 从 [Privacy Service概述](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans) 页面，以了解在为Analytics数据设置标签之前需要提出哪些问题。
1. **设置您的数据保留策略。** Adobe 需要数据保留策略来处理数据隐私数据访问/删除请求。有关更多信息，请参阅[数据保留常见问题解答](/help/technotes/data-retention.md)。要使用Privacy ServiceAPI，您必须确保在Adobe Analytics中设置数据保留期。
1. **熟悉数据隐私标签、Adobe Analytics ID、命名空间和ID扩展。**&#x200B;请参阅 [Analytics 变量的数据隐私标签](/help/admin/c-data-governance/data-labeling/gdpr-labels.md)和[标签设置最佳实践](/help/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)。
1. **向报表包中的每个变量分配身份、敏感性和数据管理标签。**&#x200B;每次创建新报表包或在现有报表包中启用新变量时，都需要对标签设置进行审核。此外，在启用新的解决方案集成时也需要审核标签设置，因为这些集成会公开可能要求设置标签的新变量。重新实施您的移动应用程序或网站时，可能会改变现有变量的使用方式，这或许也需要更新标签。请参阅[为报表包数据设置标签](/help/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)。
1. **连接到 Adobe 数据隐私 API 并提交访问和删除请求。** 作为 Adobe Analytics 客户，您可以通过调用 [ Adobe Experience Privacy Service API ](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans)，来提交单独的数据隐私请求以访问和删除客户数据。您可以在请求中提交任何 Analytics 标识符（如[标签设置最佳实践](/help/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)一节中所述）及其各自的命名空间 ID（数据源 ID）。
1. **查看和管理报表包的数据隐私设置。**&#x200B;请参阅[查看报表包的数据管理设置](/help/admin/c-data-governance/data-labeling/gdpr-view-settings.md)。
