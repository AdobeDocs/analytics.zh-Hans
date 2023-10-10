---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4134eed3cb97c478304988123196b0c906c86560
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 68%

---

# 当前的 Adobe Analytics 发行说明（2023 年 10 月）

**上次更新日期**：2023 年 10 月 4 日

10月发行说明涵盖2023年10月4日至2023年10月25日的发行期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **管理组件时可用的新列** | 在管理组件时，现在有以下新列可用：<ul><li>用在<p>可在[计算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)和[区段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)中找到此列。</p></li><li>上次使用时间<p>可在[计算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)、[分段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)和[警报管理器](/help/components/c-alerts/alert-manager.md)中找到此列。</p></li></ul><p>此信息可帮助您确定某个组件是否对组织中的用户有用、在何处使用该组件以及是否需要删除或修改该组件。可使用数据词典配合此信息帮助您跟踪并更好地了解如何在您的组织中使用组件。</p> | 2023 年 9 月 20 日 | 2023 年 10 月 4 日 |
| **报表活动管理器增强功能** | 通过报告活动管理器，可查看组织中每个报表包的报告容量。通过它，管理员可详细了解报告消耗情况，从而轻松地诊断和修复在报告高峰期出现的容量问题。以下是报表活动管理器中现在提供的一些增强功能： <ul><li>限制后续请求：除了取消当前请求之外，管理员现在还可以限制定义时间段内的请求。 管理员可以按请求、项目和用户限制请求。</li><li>除了利用率和容量量度之外，报告活动管理器现在还包含更多有关报告活动的数据：复杂性列、用户列和连接列。</li><li>在报表活动管理器中所做的所有取消和限制现在都可在审核日志中看到。 管理员可以使用审核日志查看当前取消的内容。 在报表活动管理器或审核日志中，取消操作不可撤销。</li></ul><p>有关更多信息，请参阅 [报表活动管理器概述](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 2023 年 10 月 17 日 | 2023 年 10 月 23 日 |
| **Data Warehouse 改进** | 创建 Data Warehouse 请求时，现在可配置云帐户以用作报告目标。有以下云帐户类型可用于发送数据：<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>电子邮件（以前有此选项可用）</li></ul>FTP、SFTP、Azure Blob 和 S3 仍然可用作报告目标，但不再推荐使用。<p>创建和管理 Data Warehouse 请求时的用户体验也得到了改进。有关更多信息，请参阅[创建 Data Warehouse 请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)和[管理 Data Warehouse 请求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=zh-Hans)。 | 2023 年 9 月 12 日 | 2023 年 10 月 25 日 |
| **将 Adobe Analytics 项目和其中包括的任何组件迁移到 Customer Journey Analytics** | 现在可将 Adobe Analytics 项目迁移到 Customer Journey Analytics。此过程简化了从 Adobe Analytics 到 Customer Journey Analytics 的过渡。 <p>将项目迁移到 Customer Journey Analytics 时，资源将从 Adobe Analytics 报表包映射到 Customer Journey Analytics 数据视图。</p> <p>从 Adobe Analytics 界面将项目迁移到 Customer Journey Analytics。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | 不适用 | 2023 年 10 月 9 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了Target/Analytics UI中未显示A4T报表的问题。 (AN-329375、AN-329745和AN-330026)

AN-313983、AN-324189、AN-325095、AN-325677、AN-325886、AN-326068、AN-326360、AN-326458、AN-327290、AN-327315、AN-327353、AN-327505、AN-327589、AN-327609、AN-327922、AN-328110、AN-328222、AN-328261、AN-328496、AN-328577、AN-328629、AN-328736、AN-328888、AN-328899、AN-328902、AN-328921 AN-328958； AN-329208； AN-329277； AN-329332； AN-329334； AN-329335； AN-329336； AN-329357； AN-329385； AN-329387； AN-329397； AN-329463； AN-329501； AN-329504； AN-329505； AN-329515； AN-329524； AN-329526； AN-329534； AN-329539； AN-329541； AN-329543； AN-329545； AN-329564； AN-329570； AN-329623； AN-329624 AN-329636； AN-329646； AN-329647； AN-329668； AN-329701； AN-329737； AN-329741； AN-329751； AN-329812； AN-329813； AN-329821； AN-329824； AN-329833； AN-329848； AN-329852； AN-329861； AN-329863； AN-329874； AN-329882； AN-329911； AN-329917； AN-329942； AN-329954； AN-329968； AN-329971； AN-329982； AN-330044 AN-330052； AN-330131； AN-330132； AN-330230； AN-330352； AN-330367； AN-330541； AN-330599

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **AdobeExperience Edge点击的完整IP模糊处理** | 2023 年 9 月 27 日 | 对来自Experience Edge的点击的IP模糊处理将于2023年10月晚些时候更新。 在4月，Experience Edge添加了对IP地址进行模糊处理的功能。 当时，由于Adobe Analytics处理来自Experience Edge的点击的方式，Analytics仅支持IP的部分模糊处理。 当客户为Experience Edge选择完全模糊处理时，Analytics仅收到部分模糊处理的IP。 实施此更改后，Analytics将收到完全模糊处理的IP。 |
| **Adobe Analytics Livestream - Analytics 2.0 API** | 2023 年 9 月 27 日 | 客户现在可以访问 [Adobe Analytics直播流的端点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) 在Adobe Analytics 2.0 API下，而不是在其之前的位置（使用1.4 API）。 请注意，使用Adobe I/OJWT凭据的客户必须在2025年1月1日之前迁移到Adobe I/OOAuth服务器到服务器凭据。 （请参阅下面的EOL通知中的详细信息。） |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。**2023 年 4 月**&#x200B;自动更新了任何以前安排在 2023 年 12 月 31 日之后到期的报告，并将其恢复为 2023 年 12 月 31 日到期。此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports &amp; Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用[!UICONTROL 发布列表]。您将无法创建新的[!UICONTROL 发布列表]或访问现有的发布列表以发送或安排 [!UICONTROL Analysis Workspace] 项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)以了解详情。如有任何问题，请与您组织的 Adobe 账户经理联系。 |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.25.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
