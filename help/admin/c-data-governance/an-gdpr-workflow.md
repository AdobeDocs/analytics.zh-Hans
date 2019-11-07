---
description: 'null'
title: 隐私工作流程
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: dcb07f8717337da904b252864eb7f800f1728231

---


# 隐私工作流程

此工作流程概述您需要采取哪些步骤来准备 Adobe Analytics 实施，以便支持数据主体的数据隐私访问和删除权利。

| 任务描述 | 说明和更多信息的链接 |
|--- |--- |
| **第 1 步**：确保任何可能包含数据隐私相关数据的报表包均被映射到您的 Experience Cloud（或 IMS）组织。数据隐私请求是使用 Experience Cloud 组织提交的，并且将应用于由该组织声明的所有报表包。请求将不会应用于未映射到该组织的报表包，即使它们属于您的登录公司也是如此。 | 请参阅[将报表包映射到组织](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)。 |
| **第2步**:设置数据保留策略。 | 为了使 Adobe 能够为数据隐私数据访问/删除请求提供服务，需要设置数据保留策略。有关更多信息，请参阅 [Analytics 数据保留常见问题解答](/help/technotes/data-retention.md)。 |
| **第 3 步**：熟悉 DULE/数据隐私标签、Adobe Analytics ID、命名空间和 ID 扩展。 | 请阅读本文档集中的以下主题：<ul><li>[Analytics 变量的数据隐私标签](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[标签设置最佳实践](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **第 4 步**：向报表包中的每个变量分配身份、敏感性和数据管理标签。注意：请记住，每次创建新报表包后或在现有报表包中启用新变量时，都需要对标签设置进行审核。当启用新的解决方案集成时，您可能也需要审核标签设置，因为这些集成将出现要求设置标签的新变量。重新实施您的移动应用程序或网站时，可能会改变现有变量的使用方式，这或许也需要更新标签。 | 按照[标签报表包数据](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)中的说明操作。 |
| **第 5 步**：连接到 Adobe 数据隐私 API 并提交访问和删除请求。 | As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API](https://www.adobe.io/apis/experienceplatform/gdpr.html). 您可以在请求中提交任何 Analytics 标识符（如[标签设置最佳实践](/help/admin/c-data-governance/gdpr-analytics-ids.md)一节中所述）及其各自的命名空间 ID（数据源 ID）。 |
| **第 6 步**：查看并管理报表包的数据隐私设置。 | 按照[查看报表包的“数据管理设置”](/help/admin/c-data-governance/gdpr-view-settings.md)中的说明操作。 |
