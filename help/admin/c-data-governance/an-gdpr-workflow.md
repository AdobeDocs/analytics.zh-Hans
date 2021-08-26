---
description: 概述您可以采取哪些步骤来启用 Adobe Analytics 实施，以便支持数据主体的数据隐私访问和删除权利。
title: 隐私工作流程
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 58%

---

# 隐私工作流程

此工作流程概述您需要采取哪些步骤来准备 Adobe Analytics 实施，以便支持数据主体的数据隐私访问和删除权利。

1. **设置您的数据保留策略。** Adobe为数据隐私数据访问/删除请求提供服务时，需要使用数据保留策略。有关更多信息，请参阅[数据保留常见问题解答](/help/technotes/data-retention.md)。
1. **熟悉 DULE/数据隐私标签、Adobe Analytics ID、命名空间和 ID 扩展。** 请参 [阅Analytics变量的数据隐私标签](/help/admin/c-data-governance/gdpr-labels.md) 和标签 [设置最佳实践](/help/admin/c-data-governance/gdpr-analytics-ids.md)。
1. **向报表包中的每个变量分配身份、敏感性和数据管理标签。** 每次创建新报表包或在现有报表包中启用新变量时，都需要对标签设置进行审核。此外，还可以在启用新解决方案集成时查看标签设置，因为它们可能会显示可能需要标签设置的新变量。 重新实施移动设备应用程序或网站可能会更改现有变量的使用方式，这也需要更新标签。 请参阅[为报表包数据设置标签](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) 。
1. **连接到 Adobe 数据隐私 API 并提交访问和删除请求。**&#x200B;作为 Adobe Analytics 客户，您可以通过调用 [Adobe Experience Cloud 数据隐私 API](https://www.adobe.io/apis/experienceplatform/gdpr.html)，来提交单独的数据隐私请求以访问和删除客户数据。您可以在请求中提交任何 Analytics 标识符（如[标签设置最佳实践](/help/admin/c-data-governance/gdpr-analytics-ids.md)一节中所述）及其各自的命名空间 ID（数据源 ID）。
1. **查看并管理报表包的数据隐私设置。** 请参 [阅查看报表包的数据管理设置](/help/admin/c-data-governance/gdpr-view-settings.md)。
