---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b0c97e4f9d3243e233999cf80f1d742a676f4023
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 85%

---

# 当前 Adobe Analytics 发行说明（2023 年 6 月）

**上次更新日期**：2023 年 7 月 10 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 版本亮点 {#highlights}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **配置云帐户存储位置以摄取分类数据** | 您现在可以管理用于分类集自动化的云帐户存储位置。<p>[了解详情](/help/components/locations/configure-import-accounts.md)</p> |  | 2023 年 7 月 10 日 |
| **数据修复过滤器增强功能** | 在数据修复中增加了三个过滤改进：<ul><li>按一个变量筛选以修改第二个变量。 例如，如果 `eVar2` 包含“@”，然后删除 `eVar3`.</li><li>筛选数字或非数字值</li><li>使用AND应用多个过滤器。 例如，其中 `eVar2="a"` 和 `eVar3="b"`</li></ul>[了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **用链接共享项目（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](../analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)<p>默认启用此功能，而系统管理员可禁用此功能。[了解详情](../analyze/analysis-workspace/user-preferences.md#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 7 日 |
| **分类集的新增功能** | [分类集](/help/components/classifications/sets/overview.md) 已更新若干新功能：<ul><li>**合并**：将分类集合并到一个合并的分类集中。 合并的分类集可以像其他分类集一样使用，也可以在Customer Journey Analytics中用作查找数据集。 [了解详情](../components/classifications/sets/consolidations/manage.md)</li><li>**规则**：根据分类集中的规则自动对值分类。 [了解详情](../components/classifications/sets/manage/rules.md)</li><li>**自动导入**：自动从云存储目标导入分类数据。 [了解详情](../components/classifications/sets/manage/schema.md)</li></ul> | | 2023 年 6 月 7 日 |
| **新 AppMeasurement 变量** | 变量 `doubleEncodeLinkParameters` 可适应一些少见的情况，其中实施在链接跟踪变量中为多字节字符编码。大多数实施无需定义此变量。[了解详情](../implement/vars/config-vars/doubleencodelinkparameters.md) |  | 2023 年 6 月 7 日 |
| **数据馈送导出到安全目标** | 现在可以将数据馈送发送到以下云存储目标：<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>不再推荐以前可用的目标（FTP、SFTP、S3 和 Azure Blob）。[了解详情](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=zh-Hans) | 2023 年 6 月 12 日 | 2023 年 7 月 15 日 |
| **Workspace 中的机器人报表** | Analysis Workspace 中现在有机器人报表可用。此功能附带了几项额外功能：<ul><li>一个新维度：[机器人名称](/help/components/dimensions/bot-name.md)</li><li>两个新指标：[机器人页面查看次数](/help/components/metrics/bot-page-views.md)和[机器人发生次数](/help/components/metrics/bot-occurrences.md)。</li><li>一个新的计算指标模板：[机器人页面查看率](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>一个新的 Workspace 报表：机器人报表</li></ul>新维度和指标包含自 2023 年 3 月起开始回填的数据。 |  | 2023 年 6 月 7 日 |

{style="table-layout:auto"}

## 其他新增功能或更新后的功能 {#other}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **从自由格式表中删除包含动态维度的行** | 现在可在 Analysis Workspace 的自由格式表中使用 x 图标快速地删除包含动态维度的特定行。这样做时，将自动应用“始终排除项目”过滤规则。<p>而以前只有在“过滤器”对话框中手动创建规则才能删除包含动态维度的行。[了解详情](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **在面板中新增一个用于添加可视化效果的按钮** | Analysis Workspace 中每个面板的底部现在都有一个新按钮，通过它，可快速地添加可视化效果。 <p>而以前只有从左边栏拖动可视化效果、重复或复制现有的可视化效果或创建空白面板才能将可视化效果添加到面板。[了解详情](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **深层链接（移动应用程序）** | 使用户可发送记分卡的链接，而这些链接将引导用户直接进入应用程序中的记分卡项目。这样使得可更轻松地从不太熟悉技术的受众共享项目和提高参与度。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | 不适用 | 2023 年 5 月 17 日 |
| **动态下拉筛选器** | 我们正在引入一种新类型的下拉筛选器，它根据面板的报表范围内的数据和其他下拉筛选器中的值确定可用的值。可通过在按住 [!UICONTROL Shift] 的同时将维度拖入面板拖放区域而使用动态下拉筛选器。通过在按住 [!UICONTROL Shift] 的同时将一组维度项拖入面板拖放区域，静态下拉筛选器保持不变。[了解详情](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 2023 年 6 月 14 日 |
| **更新后的 Analytics 学习页面** | Adobe Analytics 登陆页面上的“学习”选项卡现在包含以下增强：<ul><li>改进了设计，其中在单个页面上展示更多学习内容并改进了导航</li><li>可根据经验级别（初学者、中级和高级）使学习内容个性化</li></ul>[了解详情](/help/analyze/landing.md) | 2023 年 6 月 27 日 | 2023 年 6 月 30 日 |
| **为 Analysis Workspace 中的组件排序** | 在 Analysis Workspace 中的左边栏或数据词典中查看组件时，现在有一个新的排序选项可用。可按“推荐”（最常用的那些组件）、“字母顺序”或“分类”（类型）为组件排序。<p>而以前只能搜索或过滤组件。[了解详情](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | 不适用 | 2023 年 6 月 7 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

AN-311878；AN-313968；AN-314130；AN-315701；AN-315761；AN-316613；AN-317563；AN-318829；AN-319009；AN-319043；AN-319066；AN-319166；AN-319245；AN-319271；AN-319381；AN-319391；AN-319482；AN-319621；AN-319637；AN-319676；AN-320176；AN-320221；AN-320225；AN-320286；AN-320312；AN-320316；AN-320449；AN-320477；AN-320492；AN-320538；AN-320556；AN-320569；AN-320679；AN-320684；AN-320786；AN-320802；AN-320811；AN-320812；AN-320815；AN-321032；AN-321033；AN-321070；AN-321096；AN-321105；AN-321122；AN-321337；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **购买 ID 和事件 ID（事件序列化）在 37 个月后到期** | 2023 年 5 月 25 日 | 即将发布的 Analytics 点击处理引擎面向 **2023 年 6 月末或 2023 年 7 月初**&#x200B;版本，将开始强制购买 ID 和事件 ID（事件序列化）在 37 个月后到期。购买 ID 和事件 ID 目前在 Adobe Analytics 中永不到期。一旦查看/使用购买 ID 或事件 ID，以后无论何时的任何点击都将该购买或事件标为重复。在新的处理引擎发布后：<ul><li>购买 ID 和事件 ID 始终在 37 个月后到期。</li><li>如果自查看购买 ID 或事件 ID 以来已有 37 个月，则不再将它视为重复的购买或事件。</li><li> 如果正在“重用”大于 37 个月之前的购买 ID 或事件 ID，则不再将其视为重复。</li></ul> |
| **迁移到Adobe I/OOAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用Adobe I/OJWT凭据的Adobe Analytics API和Livestream客户必须通过以下方式迁移到Adobe I/OOAuth服务器到服务器凭据 **2025年1月1日**. 有关更多详细信息和时间表，请参阅下表中的终止使用通知。 |
| **伦敦数据中心的 Adobe Analytics 数据馈送和 Data Warehouse 出口使用新 IP** | 2023 年 4 月 27 日 | 这涉及伦敦数据中心内将数据馈送请求和/或 Data Warehouse 报表传送到 FTP/SFTP 服务的客户。应将以下 IP 地址范围添加到防火墙配置以允许访问： <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到Adobe I/OOAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用Adobe I/OJWT凭据的Adobe Analytics API和Livestream客户必须通过以下方式迁移到Adobe I/OOAuth服务器到服务器凭据 **2025年1月1日**. 从2024年5月1日开始，Adobe I/O不允许创建新的JWT凭据。 使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用OAuth的新旧应用程序实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。在 **2023 年 4 月**，任何计划在 2023 年 12 月 31 日之后到期的报告将会自动更新并恢复到 2023 年 12 月 31 日到期。此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports &amp; Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用[!UICONTROL 发布列表]。您将无法创建新的[!UICONTROL 发布列表]或访问现有的发布列表以发送或安排 [!UICONTROL Analysis Workspace] 项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)以了解详情。如有任何问题，请与您组织的 Adobe 账户经理联系。 |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
