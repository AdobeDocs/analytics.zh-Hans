---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 890742781a59532828003f8ba660043b9f1c73a1
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 87%

---

# 当前 Adobe Analytics 发行说明（2023 年 5 月）

**上次更新日期**：2023 年 5 月 11 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## Adobe Analytics 的新增或更新功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **非生产沙盒的回填** | 在非生产沙盒中创建 Analytics 源连接器数据流时，非生产沙盒中的回填将限制为 3 个月。生产沙盒的时间将保持在 13 个月。 | 不适用 | 2023 年 4 月 26 日 |
| **用链接共享项目（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans#share-public-link)<p>默认启用此功能，而系统管理员可禁用此功能。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=zh-Hans#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 |
| **更新了 Analytics 功能板应用程序（移动应用程序）的主屏幕** | 通过新近更新的主屏幕，可在一个合并的记分卡列表中查看您的所有记分卡。如果您可用一个登录名访问多个组织，则在一个列表中即可找到所有来自您这些组织的记分卡。 | 不适用 | 2023 年 5 月 10 日 |
| **为 Analysis Workspace 中的组件排序** | 在 Analysis Workspace 中的左边栏或数据词典中查看组件时，现在有一个新的排序选项可用。可按“推荐”（最常用的那些组件）、“字母顺序”或“分类”（类型）为组件排序。<p>而以前只能搜索或过滤组件。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=zh-Hans)</p> | 不适用 | 2023 年 5 月 17 日 |
| **从自由格式表中删除包含动态维度的行** | 现在可在 Analysis Workspace 的自由格式表中使用 x 图标快速地删除包含动态维度的特定行。这样做时自动应用“不等于”过滤规则。<p>而以前只有在“过滤器”对话框中手动创建规则才能删除包含动态维度的行。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=zh-Hans)</p> | 不适用 | 2023 年 5 月 17 日 |
| **在面板中新增一个用于添加可视化效果的按钮** | Analysis Workspace 中每个面板的底部现在都有一个新按钮，通过它，可快速地添加可视化效果。 <p>而以前只有从左边栏拖动可视化效果、重复或复制现有的可视化效果或创建空白面板才能将可视化效果添加到面板。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#add-visualizations-to-a-panel)</p> | 不适用 | 2023 年 5 月 17 日 |
| **深层链接（移动应用程序）** | 使用户可发送记分卡的链接，而这些链接将引导用户直接进入应用程序中的记分卡项目。这样使得可更轻松地从不太熟悉技术的受众共享项目和提高参与度。 | 待定 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

AN-312098、AN-318309、AN-316675、AN-318173、AN-310359、AN-317613、AN-318836、AN-315744、AN-311772、AN-318719、AN-314074、AN-316651<!--"Verified" status-->、AN-318602、AN-315961、AN-317534、AN-318607、AN-316498、AN-316648、AN-318244、AN-317747、AN-318432、AN-318231、AN-317590、AN-318415、AN-318154、AN-316647、N-314417、AN-317614、AN-317725、AN-318114、AN-317876、AN-318052、AN-317966、AN-316477、AN-318036、AN-317931、AN-318045、AN-316246、AN-317281、AN-317879、AN-308077、AN-317708、AN-316115、AN-315963

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **迁移到AdobeIO OAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | Adobe Analytics API和使用AdobeIO JWT凭据的实时流客户必须通过 **2025年1月1日**. 有关更多详细信息和时间表，请参阅下表中的终止通知。 |
| **注意：伦敦数据中心的 Adobe Analytics 数据馈送和 Data Warehouse 出口使用新 IP** | 2023 年 4 月 27 日 | 对于伦敦数据中心内将数据馈送请求和/或 Data Warehouse 报告传送到 FTP/SFTP 服务的客户，应将以下 IP 地址范围添加到防火墙配置以允许访问： <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
| **设备查找过程现在将一个第三方用于所有设备查找** | 2023 年 3 月 3 日 | 2023 年 3 月 2 日，作为推出客户端提示支持的一部分，我们更新了设备查找过程以将一个第三方用于所有设备查找。我们以前将该第三方仅用于移动设备查找。在此推出的过程中，不当地为一些桌面操作系统标注了“mobile”一词（如“Mobile OS X 10.15.7”而非“OS X 10.15.7”）。<p>在 Adobe 的 4 月发行版中，我们将更正这些名称。将追溯地更新 Analytics 和 CJA 报告，因为其报告基于作为事件数据的一部分而记录的 ID 查找操作系统名称。在更新与 ID 对应的查找值后，将更正所有报告，包括历史数据。对于 [!UICONTROL 数据馈送] 客户，如果您在报告时使用类似的查找流程，则更改具有追溯性。 不过，如果您将操作系统值存储在事件数据中，则报告将仅在以后更新。有关更多详细信息，请参阅[操作系统](/help/components/dimensions/operating-systems.md)。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到AdobeIO OAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | Adobe Analytics API和使用AdobeIO JWT凭据的实时流客户必须通过 **2025年1月1日**. 从2024年5月1日开始，AdobeIO将不允许创建新的JWT凭据。 使用JWT的客户必须创建新的OAuth服务器到服务器凭据，或将其现有的JWT凭据迁移到OAuth服务器到服务器凭据。 客户还必须更新其客户端应用程序才能使用新的OAuth服务器到服务器凭据。 <ul><li>[从服务帐户(JWT)凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的OAuth服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |
| **终止日语版功能手机跟踪服务** | 2023 年 3 月 21 日 | 仅针对我们的日本客户：**2023 年 5 月底**&#x200B;将终止日语版功能手机跟踪服务 (mod_ktrack)。由此给您带来的不便，我们深表歉意，但我们恳请您卸载或禁用安装在您 Apache 服务器上的这些模块。请参阅[本文档](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf)中的第 27 页和第 28 页以供参考。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。<p>2023 年 12 月 31 日，我们将终止许多相关的报告和分析功能，包括但不限于：Reports &amp; Analytics、数据提取和 DL 报告。2023 年 12 月 31 日之后，将不再发送任何计划报告。在 **2023 年 4 月**，任何计划在 2023 年 12 月 31 日之后到期的报告将会自动更新并恢复到 2023 年 12 月 31 日到期。此外，您不能再安排 2023 年 12 月 31 日之后的未来报告。 |
| **终止使用[!UICONTROL 人员]指标** | 2023 年 3 月 9 日 | 启用 [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html) 后，与 Device Co-op 相关的人员量度不再相关。我们将在 2023 年 5 月 8 日删除[!UICONTROL 人员]量度。届时，我们会将其数据重定向到[!UICONTROL 独特访客]量度，以防止项目、区段和计算量度出现中断。<p>**注释**：与跨设备分析相关的[[!UICONTROL 人员]量度](/help/components/metrics/people.md)不受本公告影响。 |
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
