---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 49c4acb38a96b5fd6a8cd25258628adc9a68074c
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 53%

---

# 当前 Adobe Analytics 发行说明 (2023 年 6 月)

**上次更新时间**：2023 年 6 月 1 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 版本亮点 {#highlights}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **用链接共享项目（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](../analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)<p>默认启用此功能，而系统管理员可禁用此功能。[了解详情](../analyze/analysis-workspace/user-preferences.md#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 7 日 |
| **分类集的新增功能** | [分类集](/help/components/classifications/sets/overview.md) 已更新若干新功能：<ul><li>**合并**：将分类集合并到一个合并的分类集中。 合并的分类集可以像其他分类集一样使用，或者在CJA中用作查找数据集。 [了解详情](../components/classifications/sets/consolidations/manage.md)</li><li>**规则**：根据分类集中的规则自动对值分类。 [了解详情](../components/classifications/sets/manage/rules.md)</li><li>**自动导入**：自动从云存储目标导入分类数据。 [了解详情](../components/classifications/sets/manage/schema.md)</li></ul> | | 2023 年 6 月 7 日 |
| **新建AppMeasurement变量** | 变量 `doubleEncodeLinkParameters` 适合边缘案例，在这些案例中，实施会对链接跟踪变量中的多字节字符进行编码。 大多数实施不需要定义此变量。 [了解详情](../implement/vars/config-vars/doubleencodelinkparameters.md) |  | 2023 年 6 月 7 日 |
| **数据馈送导出的安全目标** | 数据馈送现在可以发送到以下云存储目标：<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud 平台</li></ul>不再建议以前可用的目标（FTP、SFTP、S3和Azure Blob）。 [了解详情](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=zh-Hans) |  | 2023 年 6 月 12 日 |
| **工作区中的机器人报告** | 机器人报告功能现已在Analysis Workspace中可用。 此功能附带几个附加功能：<ul><li>新维度： [机器人名称](/help/components/dimensions/bot-name.md)</li><li>两个新量度： [机器人页面查看次数](/help/components/metrics/bot-page-views.md) 和 [机器人出现次数](/help/components/metrics/bot-occurrences.md).</li><li>新的计算量度模板： [机器人页面查看率](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>新的工作区报表：机器人报表</li></ul>新维度和量度包含从2023年3月开始回填的数据。 |  | 7,2023 年 6 月 |

{style="table-layout:auto"}

## 其他新增或更新功能 {#other}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **从自由格式表中删除包含动态维度的行** | 现在可在 Analysis Workspace 的自由格式表中使用 x 图标快速地删除包含动态维度的特定行。在执行此操作时，会自动应用“始终排除项目”筛选规则。<p>而以前只有在“过滤器”对话框中手动创建规则才能删除包含动态维度的行。[了解详情](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **在面板中新增一个用于添加可视化效果的按钮** | Analysis Workspace 中每个面板的底部现在都有一个新按钮，通过它，可快速地添加可视化效果。 <p>而以前只有从左边栏拖动可视化效果、重复或复制现有的可视化效果或创建空白面板才能将可视化效果添加到面板。[了解详情](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **深层链接（移动应用程序）** | 使用户可发送记分卡的链接，而这些链接将引导用户直接进入应用程序中的记分卡项目。这样使得可更轻松地从不太熟悉技术的受众共享项目和提高参与度。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | 不适用 | 2023 年 5 月 17 日 |
| **动态下拉过滤器** | 我们正在引入一种新类型的下拉过滤器，它会根据面板报告范围内的数据和其他下拉过滤器中的值来确定可用值。 您可以通过在按住的同时将维度拖动到面板拖放区域中使用动态下拉过滤器 [!UICONTROL Shift]. 静态下拉筛选器保持不变，方法是将一组维度项目拖动到面板拖放区域中，同时保持 [!UICONTROL Shift]. [了解详情](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 2023 年 6 月 14 日 |
| **更新的Analytics学习页面** | Adobe Analytics登录页面上的“学习”选项卡现在包含以下增强功能：<ul><li>改进了设计，通过改进的导航在单个页面上显示更多学习内容</li><li>能够按体验级别（初级、中级和高级）个性化学习内容</li></ul>[了解详情](/help/analyze/landing.md) |  | 30,2023 年 6 月 |
| **为 Analysis Workspace 中的组件排序** | 在 Analysis Workspace 中的左边栏或数据词典中查看组件时，现在有一个新的排序选项可用。可按“推荐”（最常用的那些组件）、“字母顺序”或“分类”（类型）为组件排序。<p>而以前只能搜索或过滤组件。[了解详情](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | 不适用 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

-311878、-313968、AN-314130、AN-315701、AN-315761、AN-316613、AN-317563、AN-318829、AN-319009、AN-319043、AN-319066、AN-、AN-、AN-319166、AN-319245、AN-319271、AN-319381、AN-319391、AN-319482、AN-319621、AN-319637、AN-319676、AN-320176、AN-320221、AN-320225、AN-320286、AN-320312、AN-320316、AN-320449、AN-320477、AN-320492、AN-320538、AN-320556、AN-320569、AN-320679、AN-320684、AN-320786、AN-320802、AN-320811、AN-320812、AN-320815、AN-321032、AN-321033、AN-321070、AN-321096、AN-321105、AN-321122、AN-321337；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **购买ID和事件ID将于37个月后过期（事件序列化）** | 25,2023 年 5 月 | 即将发行的Analytics点击处理引擎版本，定位在中发行 **2023年6月下旬或2023年7月初**，将开始强制购买ID和事件ID（事件序列化）在37个月后过期。 目前，购买ID和事件ID在Adobe Analytics中永不过期。 一旦“购买ID”或“事件ID”被查看/使用，无论何时该购买或事件都会被标记为重复，而任何未来的点击都不会发生这种情况。 在新的处理引擎版本中：<ul><li>购买ID和事件ID始终在37个月后过期。</li><li>如果自显示购买ID或事件ID以来已有37个月，则不再将它视为重复购买或事件。</li><li> 如果您“重复使用”超过37个月前的购买ID或事件ID，则不再将它们视为重复项。</li></ul> |
| **迁移到AdobeIO OAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用AdobeIO JWT凭据的Adobe Analytics API和Livestream客户必须通过以下方式迁移到AdobeIO OAuth服务器到服务器凭据 **2025年1月1日**. 有关更多详情和时间表，请参阅下表中的生命周期结束通知。 |
| **伦敦数据中心的Adobe Analytics数据馈送和Data warehouse出口使用的新IP** | 2023 年 4 月 27 日 | 这与伦敦数据中心的客户有关，这些客户具有要提交到FTP/SFTP服务的数据馈送请求和/或Data warehouse报表。 应将以下IP地址范围添加到您的防火墙配置中，以便允许访问： <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到AdobeIO OAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用AdobeIO JWT凭据的Adobe Analytics API和Livestream客户必须通过以下方式迁移到AdobeIO OAuth服务器到服务器凭据 **2025年1月1日**. 从2024年5月1日开始，AdobeIO不允许创建新的JWT凭据。 使用JWT的客户必须创建新的OAuth服务器到服务器凭据，或将其现有JWT凭据迁移到OAuth服务器到服务器凭据。 客户还必须更新其客户端应用程序才能使用新的OAuth服务器到服务器凭据。 <ul><li>[从服务帐户(JWT)凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的OAuth服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
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
