---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 631c217d45b2504b1faa3bb2e585d3dcdfac128c
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 79%

---

# 最新Adobe Analytics发行说明（2022年10月）

**上次更新**:2022年10月5日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新

## Adobe Analytics 的新增或更新功能

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| **[!UICONTROL 关键量度摘要]** 可视化 | 的 [!UICONTROL 关键量度摘要] 通过可视化图表，您可以了解重要量度在单个时间范围内的趋势。 它还允许您在两个时间范围内比较量度表现。 [了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=en) | 从2022年10月5日开始分阶段推出 |
| 新建 **[!UICONTROL 分类集]** 用户体验 | 新的用户体验提供了一个用于管理分类和规则的单一界面，并可提高客户拥有的分类数据的可见性。 [了解详情](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=en) | 2022 年 10 月 5 日 |
| 移动设备应用程序： **自定义详细信息视图** | 通过自定义详细信息视图，您可以更加有针对性地了解您与受众共享的哪些信息，具体方法是让受众重点关注最重要的内容。 您可以更改与每个记分卡图块关联的详细信息视图的布局，并可以添加文本以更好地说明最终用户在数据中可能看到的内容。 [了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=zh-Hans) | 2022 年 10 月 5 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

AN-298512;AN-300117;AN-301754;AN-301584;AN-301685;AN-301783;AN-301818;AN-301825;AN-301834;AN-301965;AN-302095;AN-302189;AN-302269;AN-302290;AN-302301;AN-302348;AN-302531;AN-302533;


## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **默认登陆页面** | 2023 年 9 月 | 的 [新登陆页面](/help/analyze/landing.md) 今年早些时候引入的体验将成为 **2023年1月**. 当前页面将被弃用，每个人都需要使用新体验。 |
| **终止 [!UICONTROL 发布列表] 功能** | 2022 年 9 月 29 日 | 作为Reports &amp; Analytics生命周期终止的一部分，发布列表将在 **2023年12月**. 您将无法创建新发布列表或访问现有发布列表以发送或计划Analysis Workspace项目。 [了解详情](/help/admin/admin/publishing-list.md) |
| **[!UICONTROL 异常检测] 自动运行条件** | 2022 年 9 月 29 日 | 今天， [!UICONTROL 异常检测] 自动在时间序列自由格式表的所有列上运行。 为确保数据能够更快地用于分析和项目加载，Adobe将更改异常检测自动运行的方式。 开始 **2022年10月26日**, [!UICONTROL 异常检测] 将仅在表中的第一个量度列上自动运行。 您可以配置列设置，以便根据需要对其他列运行异常检测。 |
| **更新到新的 NetAcuity 网络运营商数据库** | 2022 年 9 月 26 日 | 原计划于 2022 年 10 月 5 日进行的本次更新已推迟到 **2023 年 1 月**。存储在 Adobe Analytics Data Warehouse 和 Analytics 数据馈送的 `carrier` 字段中的与运营商相关的信息将发生变化。过去，该列中的数据格式一直是 `<domain>:<ISP>`。Adobe 维护有内部查找表将这些 `<domain>:<ISP>` 值映射到运营商名称中，以便在 Adobe Analytics 报告工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream 等）中进行报告。查找文件 (`carrier.tsv`) 也随数据馈送一起提供，以便您能使用相同的映射。<p>此更新通过使用 NetAcuity 提供的更为准确的运营商数据库来增强运营商映射。 数据馈送中运营商列中的数据格式将继续更改。 于 `<domain>:<ISP>` 不同，它将包含运营商名称。 Adobe 将继续使用查找表，以尽可能保持与过去报告的连续性。 Adobe 应用查找的报告工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream 等） 将受益于更精确的映射。 当 Adobe 采用新的数据库时，一些映射（尤其是国际域名和 ISP 的映射）将发生更大的变化。数据馈送运营商查找文件 (`carrier.tsv`) 将维护旧映射并添加新映射。<p>Analytics Source Connector 当前未映射运营商字段，因此运营商报告当前在 Experience Platform、CJA 等中不可用。因此，使用新的运营商数据库不会影响 Experience Platform 中基于 Analytics Source Connector 提供的数据的任何内容。 |
| **改进的 IP 到地理位置映射** | 2022 年 9 月 26 日 | 我们的 IP 查找供应商 Digital Element 正在升级到新的改进数据集 (NetAcuity Pulse)，用于 IP 到地理位置映射。Adobe Analytics 原计划于 2022 年 10 月采用此新数据集，但现在将于 **2023 年 1 月**&#x200B;采用。新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p>所有 Adobe Analytics 工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream、数据馈送等） 将自动利用新的改进映射。 数据馈送中的数据格式不会发生变化。 通过 Analytics Source Connector 提供的 CJA 数据也将自动利用新的映射。 |
| **SFTP 升级** | 2022 年 9 月 19 日 | 此前，Adobe 曾表示将于 2022 年 9 月升级其安全文件传输协议 (SFTP) 服务，以提高文件传输的安全性。Adobe 于 **2022 年 9 月 20 日**&#x200B;执行了此升级。进行此更改后，不再支持某些 SFTP 客户端配置。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hans)详述的更改一致。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。如果您有任何问题，请联系您的客户关怀代表以获取 Data Workbench 的替代解决方案。 |
| **由于 Google 客户端提示而更新设备查找** | 2022 年 8 月 19 日 | 从 **2022 年 10 月 26 日**&#x200B;开始，在为来自 Chromium 浏览器（如 Google Chrome 和 Microsoft Edge）的点击获取某些设备信息时，Adobe 除了使用 User-Agent 之外，还将开始使用客户端提示。这是为了响应 Google 的计划，该计划逐步减少从 User-Agent 字符串产生的信息，并用通过客户端提示传递的数据替代。在[此处](https://web.dev/user-agent-client-hints/)详细了解客户端提示。<p> 最迟到 10 月，AppMeasurement 和 Web SDK 集合库都将支持收集客户端提示和配置是否收集高熵客户端提示。作为此更改的一部分，Adobe 将使用 Device Atlas 进行与用户代理相关的所有设备查找。目前，Device Atlas 仅用于移动点击。这些更新可能会导致以前从 User-Agent 获取的设备信息稍有变化——尤其是浏览器、浏览器类型、操作系统、操作系统类型和移动设备。[了解详情](/help/technotes/client-hints.md) |
| **暂停 Reports &amp; Analytics 中的计划报告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，Adobe 宣布弃用特定于计划报告的多项功能，为之前宣布的 Reports &amp; Analytics 生命周期结束做准备。这些功能包括计划新报告和新数据提取的能力。<p>为响应客户延期请求并简化从 Reports &amp; Analytics 的过渡，Adobe 已决定将这些功能的访问权限延长至 **2023 年 1 月 31 日**。请注意，报告和数据提取的到期窗口仍为九个月；除非重新激活计划，否则报告和数据提取交付将在此期限结束时暂停。<p>重申一下，这些功能将于 2023 年 1 月 31 日弃用。在此日期之前，您必须将计划报告迁移到 Adobe Analytics 中可供您使用的其他机制之一。如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **在 Report Builder 中暂停计划任务** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，作为性能和交付优化工作的一部分，Adobe 在 Report Builder 中推出了对计划任务的更改。这些更改包括取消预定交付“在发生 x 次后结束”的功能。为了响应一些客户要求更多时间来探索和实施替代方案的请求，Adobe 已决定在 **2023 年 1 月 31 日**&#x200B;之前有限地恢复此功能选项。<p>您可以继续计划每小时 Report Builder 任务，并在最多发生 99 次后结束这些任务。请注意，回滚仅适用于小时任务；对于所有其他交付间隔期（每天、每周、每月和每年），“在发生 x 次后结束”不可用。请注意，此选项将于 2023 年 1 月 31 日弃用。如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。 [了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。
