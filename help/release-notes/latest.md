---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f996448224ffebd57023c8d8e4eeeccb4d6e2a47
workflow-type: ht
source-wordcount: '920'
ht-degree: 100%

---

# 当前 Adobe Analytics 发行说明（2023 年 7 月）

**上次更新日期**：2023 年 7 月 10 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **配置云帐户存储位置以摄取分类数据** | 您现在可以管理用于分类集自动化的云帐户存储位置。[了解详情](/help/components/locations/configure-import-accounts.md)<p> | 不适用 | 2023 年 7 月 10 日 |
| **“数据修复”过滤器增强功能** | 已向“数据修复”添加三项过滤改进：<ul><li>按一个变量过滤以修改第二个变量。例如，如果 `eVar2` 包含“@”，则删除 `eVar3`。</li><li>过滤数值或非数值</li><li>使用 AND 应用多个过滤器。例如，`eVar2="a"` AND `eVar3="b"`</li></ul>[了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **数据馈送导出到安全目标** | 现在可以将数据馈送发送到以下云存储目标：<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>不再推荐以前可用的目标（FTP、SFTP、S3 和 Azure Blob）。[了解详情](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=zh-Hans) | 2023 年 6 月 12 日 | 2023 年 7 月 13 日 |
| **新 AppMeasurement 变量** | 变量 `decodeLinkParameters` 可适应一些少见的情况，其中实施在链接跟踪变量中为多字节字符编码。大多数实施无需定义此变量。[了解详情](../implement/vars/config-vars/decodelinkparameters.md) |  | 2023 年 7 月 17 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

AN-307816；AN-318111；AN-318584；AN-318828；AN-320440；AN-320568；AN-320616；AN-321013；AN-321513；AN-321520；AN-321757；AN-321820；AN-321917；AN-322034；AN-322135；AN-322140；AN-322142；AN-322251；AN-322353；AN-322378；AN-322383；AN-322427；AN-322458；AN-322543；AN-322630；AN-322637；AN-322638；AN-322647；AN-322728；AN-322732；AN-322777；AN-322817；AN-322957；AN-322958；AN-323035；AN-323074；AN-323150；AN-323196；AN-323197；AN-323205；AN-323206；AN-323217；AN-323224；AN-323225；AN-323244；AN-323257；AN-323277；AN-323280；AN-323293；AN-323309；AN-323318；AN-323468；AN-323476；AN-323514；AN-323572；AN-323592；AN-323782；AN-323835

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **购买 ID 和事件 ID（事件序列化）在 37 个月后到期** | 2023 年 7 月 10 日 | 计划于 **2023 年 7 月 13 日**&#x200B;发行的 Analytics Hit 处理引擎版本，将开始强制“购买 ID”和“事件 ID”（事件序列化）在 37 个月后到期。购买 ID 和事件 ID 目前在 Adobe Analytics 中永不到期。一旦查看/使用购买 ID 或事件 ID，以后无论何时的任何点击都将该购买或事件标为重复。在新的处理引擎发布后：<ul><li>购买 ID 和事件 ID 始终在 37 个月后到期。</li><li>如果自查看购买 ID 或事件 ID 以来已有 37 个月，则不再将它视为重复的购买或事件。</li><li> 如果正在“重用”大于 37 个月之前的购买 ID 或事件 ID，则不再将其视为重复。</li></ul> |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。有关更多详细信息和时间表，请参阅下表中的终止使用通知。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。在 **2023 年 4 月**，任何计划在 2023 年 12 月 31 日之后到期的报告将会自动更新并恢复到 2023 年 12 月 31 日到期。此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
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
