---
title: 当前 Adobe Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d4868971596c43721e0d642ae3ad91c316fc6908
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 70%

---

# 当前 Adobe Analytics 发行说明 (2023 年 9 月)

**上次更新日期**：2023 年 9 月 6 日

9月发行说明涵盖2023年9月13日至2023年10月3日的发行周期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **API 2.0 中的分类集** | 提供用于保存、删除、检索、导入和导出分类集数据的 Adobe Analytics API 2.0 方法。[了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | 不适用 | 2023 年 9 月 13 日 |
| **支持新的 `correlationID` 用于A4T分类的字段** | `_experience.decisioning.propositions.scopeDetails.correlationID` 字段现在在 Adob&#x200B;&#x200B;e Analytics 源连接器架构中可用。我们将添加此ID，以轻松联接Adobe Target活动和体验事件的分类数据。 | 不适用 | 2023 年 9 月 13 日 |
| **数据仓库改进** | 现在，在创建Data Warehouse请求时，您可以配置一个云帐户以用作报表目标。 以下云帐户类型可用于发送数据：<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>电子邮件（此选项以前可用）</li></ul>FTP、SFTP、Azure Blob和S3仍可用作报表目标，但不再建议使用这些功能。<p>创建和管理Data Warehouse请求时的用户体验也得到了改进。 有关更多信息，请参阅 [创建Data Warehouse请求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/create-request/t-dw-create-request.html) 和 [管理Data Warehouse请求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=zh-Hans). | 2023 年 9 月 13 日 | 2023 年 10 月 4 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了阻止分类数据在工作区中显示的问题。 (AN-326827)

## 其他修复

AN-314882、AN-315591、AN-318165、AN-318559、AN-319031、AN-319244、AN-321657、AN-321759、AN-323099、AN-323596、AN-323640、AN-324442、AN-324921、AN-324953、AN-324977、AN-324979、AN-325124、AN-325395、AN-325433、AN-325535、AN-325693、AN-325720、AN-325835、AN-325880、AN-325957、AN-325984 AN-326054； AN-326065； AN-326136； AN-326155； AN-326162； AN-326235； AN-326317； AN-326344； AN-326357； AN-326359； AN-326433； AN-326438； AN-326440； AN-326461； AN-326464； AN-326523； AN-326553； AN-326606； AN-326635； AN-326642； AN-326652； AN-326678； AN-326769； AN-326777； AN-326830； AN-326938； AN-326949 AN-327081；AN-327082；AN-327085；AN-327103；AN-327198；AN-327225；AN-327275；AN-327358；AN-327423；AN-327561；AN-327755；AN-327896；AN-327922；AN-328128；AN-328300；AN-328428；AN-328518；AN-328554；AN-；AN-；AN-；AN-；AN-；AN-；AN-

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 不适用 | 不适用 | 不适用 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。在 **2023年4月**，则任何计划于2023年12月31日之后到期的报告都会自动更新并恢复到2023年12月31日到期。 此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports &amp; Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用[!UICONTROL 发布列表]。您将无法创建新的[!UICONTROL 发布列表]或访问现有的发布列表以发送或安排 [!UICONTROL Analysis Workspace] 项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)以了解详情。如有任何问题，请与您组织的 Adobe 账户经理联系。 |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.24.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
