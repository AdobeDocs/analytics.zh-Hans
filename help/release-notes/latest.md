---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c13e39e7bfe3d7fef07ea9ccda76255d28dde1c3
workflow-type: tm+mt
source-wordcount: '1464'
ht-degree: 100%

---

# 当前 Adobe Analytics 发行说明

**上次更新日期**：2023 年 1 月 25 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## Adobe Analytics 的新增或更新功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Workspace 中的文件夹** | 文件夹帮助您组织和分类项目以便更好地检索和访问。此外，通过一个共享的&#x200B;**[!UICONTROL 公司]**&#x200B;文件夹管理员可轻松地创建内容并与所有 Workspace 用户共享内容。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html) | 不适用 | 2023 年 1 月 11 日 |
| **默认登陆页面** | 2022 年早些时候引入的[新登陆页面](/help/analyze/landing.md)在 **2023 年 1 月 11 日**&#x200B;将成为所有用户的默认体验。传统登陆页面将被弃用，每个人都将必须使用新体验。 | 不适用 | 2023 年 1 月 11 日 |
| **项目管理器页面已弃用** | 随着新登陆页面的发布，我们弃用了&#x200B;**[!UICONTROL 项目管理器]**，如 **[!UICONTROL Adobe Analytics]** > **[!UICONTROL 组件]**&#x200B;下所列。新的登陆页面具有旧项目管理器页面的所有功能以及其他功能。了解详情 | 不适用 | 2023 年 1 月 11 日 |
| **自动保存新项目** | Analysis Workspace 现在会自动保存新创建的项目。如果由于任何原因，在手动保存新创建的项目之前，您意外地失去了对该项目的访问权限，则现在可以使用项目的恢复版本。以前，项目只有在最初手动保存后才自动保存。[了解详情](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md) | 不适用 | 2023 年 1 月 11 日 |
| **增强的用户偏好设置** | 您现在可以在用户级别配置其他偏好设置（在 [!UICONTROL 组件] > [!UICONTROL 偏好设置] 中）。当您设置用户偏好设置时，您的选择会跨越您的项目、表格和可视化图表。偏好设置页面现在包含以下新选项卡，每个选项卡包含许多新的配置选项：<ul><li>自由格式表</li><li>可视化图表</li></ul>此外，**[!UICONTROL 常规]**&#x200B;和&#x200B;**[!UICONTROL 项目]**&#x200B;选项卡上现已提供更多偏好设置。<p>以前，其中许多偏好设置只能针对单个项目、表格和可视化图表进行配置。[了解详情](/help/analyze/analysis-workspace/user-preferences.md) | 不适用 | 2023 年 1 月 11 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

AN-282634；AN-289684；AN-299597；AN-299630；AN-300128；AN-301633；AN-301683；AN-301745；AN-302238；AN-302521；AN-302601；AN-303325；AN-303363；AN-303867；AN-304120；AN-304185；AN-304221；AN-304222；AN-304510；AN-304591；AN-304872；AN-305151；AN-305159；AN-305233；AN-305235；AN-305241；AN-305250；AN-305274；AN-305292；AN-305311；AN-305314；AN-305331；AN-305335；AN-305348；AN-305372；AN-305382；AN-305442；AN-305504；AN-305517；AN-305572；AN-305584；AN-305588；AN-305612；AN-305640；AN-305663；AN-305718；AN-305723；AN-305767；AN-305769；AN-305703；AN-305711；AN-305775；AN-305883；AN-305886；AN-305882；AN-305886；AN-305916；AN-305969；AN-305997；AN-306052；AN-306088；AN-306199；AN-306214；AN-306233；AN-306251；AN-306348；AN-306372；AN-306390；AN-306413；AN-306430；AN-306514；AN-306578；AN-306612；AN-306886；AN-306893；AN-306905；AN-306984；AN-306989；AN-307038；AN-307061；AN-307062；AN-307176；AN-307209；AN-307233；AN-307257；AN-307280；AN-307292；AN-307293；AN-307318；AN-307319；AN-307320；AN-307325；AN-307368；AN-307381；AN-307403；AN-307461；AN-307480；AN-307650；AN-307767；AN-307790；AN-307813；AN-307833；AN-307835；AN-307867；AN-307899；AN-307907；AN-307934；AN-307991；AN-308031；AN-308057；AN-308240；AN-308242；AN-308302；AN-308363；AN-308373；AN-308450；AN-308591；AN-308673；AN-308725；AN-309171；

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **由于 Google 客户端提示而更新设备查找** | 2023 年 1 月 25 日 | 在设备查找中使用客户端提示的功能将于 **2023 年 2 月 16 日**&#x200B;开始可用。 <p> <p>自 2022 年 10 月起，可以使用 Web SDK 或 AppMeasurement JavaScript 库收集客户端提示。但直到 2023 年 2 月才将客户端提示纳入设备查找。届时，在为来自 Chromium 浏览器（如 Google Chrome 和 Microsoft Edge）的点击派生某些设备信息时，Adobe 除了使用 User-Agent 之外，还将开始使用客户端提示。这是为了响应 Google 的计划，该计划逐步减少从 User-Agent 字符串产生的信息，并用通过客户端提示传递的数据替代。 <p> <p>作为此更改的一部分，Adobe 将使用 Device Atlas 执行所有与 User-Agent 相关的设备查找。[了解详情](/help/technotes/client-hints.md) |
| **暂停 Reports &amp; Analytics 中的计划报告** | 2023 年 1 月 6 日 | 在此提醒一下，Adobe 将于 **2023 年 1 月 31 日**&#x200B;弃用这些功能。请注意，报告和数据提取的到期窗口仍为九个月；除非重新激活计划，否则报告和数据提取交付将在此期限结束时暂停。<p>重申一下，这些功能将于 2023 年 1 月 31 日弃用。在此日期之前，您必须将计划报告迁移到 Adobe Analytics 中可供您使用的其他机制之一。如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **在 Report Builder 中暂停计划任务** | 2023 年 1 月 6 日 | **2023 年 1 月 31 日**，作为性能和交付优化工作的一部分，Adobe 将在 Report Builder 中推出对计划任务的更改。这些更改包括取消预定交付“在发生 x 次后结束”的功能。<p>您可以继续计划每小时 Report Builder 任务，并在最多发生 99 次后结束这些任务。请注意，回滚仅适用于小时任务；对于所有其他交付间隔期（每天、每周、每月和每年），“在发生 x 次后结束”不可用。请注意，此选项将于 2023 年 1 月 31 日弃用。如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。 [了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **改进的 IP 到地理位置映射** | 2023 年 1 月 4 日 | 我们的 IP 查找供应商 Digital Element 正在升级到新的改进数据集 (NetAcuity Pulse)，用于 IP 到地理位置映射。Adobe Analytics 原计划于 2022 年 10 月采用此新数据集，但现在将于 **2023 年 1 月 11 日**&#x200B;采用。新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p>所有 Adobe Analytics 工具（Analysis Workspace、Reports &amp; Analytics、Reporting API、Data Warehouse、LiveStream、Analytics Data Feeds 等）都将自动利用新改进的映射。数据馈送中的数据格式不会发生变化。通过 Analytics Source Connector 提供的 CJA 数据将自动利用新映射。 |
| **更新到新的 NetAcuity 运营商数据库** | 2023 年 1 月 4 日 | 原计划于 2022 年 10 月 5 日进行的本次更新现在将于 **2023 年 1 月 11 日**&#x200B;进行。存储在 Adobe Analytics Data Warehouse 和 Analytics 数据馈送的 `carrier` 字段中的与运营商相关的信息将发生变化。过去，该列中的数据格式一直是 `<domain>:<ISP>`。Adobe 维护有内部查找表将这些 `<domain>:<ISP>` 值映射到运营商名称中，以便在 Adobe Analytics 报告工具（Analysis Workspace、Reports &amp; Analytics、Reporting API、Data Warehouse、LiveStream 等）中进行报告。查找文件 (`carrier.tsv`) 也随数据馈送一起提供，以便您能使用相同的映射。<p>此更新通过使用 NetAcuity 提供的更为准确的运营商数据库来增强运营商映射。 数据馈送中运营商列中的数据格式将继续更改。 与 `<domain>:<ISP>` 不同，它将包含运营商名称。 Adobe 将继续使用查找表，以尽可能保持与过去报告的连续性。 Adobe 应用查找的报告工具（Analysis Workspace、Reports &amp; Analytics、Reporting API、Data Warehouse、LiveStream 等） 将受益于更精确的映射。 当 Adobe 采用新的数据库时，一些映射（尤其是国际域名和 ISP 的映射）将发生更大的变化。数据馈送运营商查找文件 (`carrier.tsv`) 将维护旧映射并添加新映射。<p>Analytics Source Connector 当前未映射运营商字段，因此运营商报告当前在 Experience Platform、CJA 等中不可用。因此，使用新的运营商数据库不会影响 Experience Platform 中基于 Analytics Source Connector 提供的数据的任何内容。 |
| **更新了流量尖峰通知指南** | 2022 年 11 月 18 日 | 以前的指南严格基于点击量。[新指南](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)基于报告包大小和百分比增长的组合。 |

{style=&quot;table-layout:auto&quot;}

## 生命周期终止通知

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports and Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用发布列表。您将无法创建新的发布列表或访问现有的发布列表以发送或安排 Analysis Workspace 项目。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。请参阅 [Data Workbench 生命周期结束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html)以了解详情。如有任何问题，请与您组织的 Adobe 客户经理联系。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
