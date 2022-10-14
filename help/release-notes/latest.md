---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 51fe791a0a0ea45aab3b19f9639d8cc1a10ec114
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 94%

---

# 当前的 Adobe Analytics 发行说明（2022 年 10 月）

**上次更新时间**：2022 年 10 月 14 日

Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新

## Adobe Analytics 的新增或更新功能

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| **[!UICONTROL 关键指标摘要]**&#x200B;可视化 | 通过[!UICONTROL 关键指标摘要]可视化，可了解某个重要的指标在单个时间范围内的趋势如何。通过它，还可比较指标在两个时间范围内的表现。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=zh-Hans) | 已从 2022 年 10 月 5 日开始分阶段推出 |
| 新的&#x200B;**[!UICONTROL 分类集]**&#x200B;用户体验 | 新用户体验提供单个界面以管理分类和规则，并更容易看到客户拥有的分类数据。[了解详情](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=zh-Hans) | 2022 年 10 月 5 日 |
| 移动应用程序：**自定义详细信息视图** | 通过自定义详细信息视图，可通过让受众关注最重要的内容而使与受众共享的信息更有针对性。可更改与每个记分卡图块关联的详细视图的布局，并可添加文本以更好地解释最终用户可能在数据中看到的内容。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=zh-Hans) | 2022 年 10 月 5 日 |
| **不区分大小写的多值变量** | 对于不区分大小写的多值变量，存储在数据馈送中的 `mvvar1` 至 `mvvar3` 中的值将不再自动变为小写。而是数据馈送（以及通过 Analytics Source Connector 传递到 Adobe Experience Platform 和 CJA 的数据）将反映从页面传入的原有大小写形式。 | 2022 年 10 月 24 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

AN-298512；AN-300117；AN-301754；AN-301584；AN-301685；AN-301783；AN-301818；AN-301825；AN-301834；AN-301965；AN-302095；AN-302189；AN-302269；AN-302290；AN-302301；AN-302348；AN-302531；AN-302533；


## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **由于 Google 客户端提示而更新设备查找** | 2022 年 10 月 14 日 | 最初计划于2022年10月26日在设备查找中使用客户端提示，现已推迟到 **2023年1月**. <p> <p>从2022年10月起，可以通过Web SDK或AppMeasurement JavaScript库收集客户端提示。 但是，在2023年1月之前，客户端提示不会纳入设备查找中。 届时，在为来自Chromium浏览器(如Google Chrome和Microsoft Edge)的点击获取某些设备信息时，Adobe将开始在用户代理之外使用客户端提示。 这是为了响应 Google 的计划，该计划逐步减少从 User-Agent 字符串产生的信息，并用通过客户端提示传递的数据替代。 <p> <p>作为此更改的一部分，Adobe 将使用 Device Atlas 进行与用户代理相关的所有设备查找。[了解详情](/help/technotes/client-hints.md) |
| **默认登陆页面** | 2022 年 9 月 29 日 | 今年早些时候引入的[新登陆页面](/help/analyze/landing.md)在 **2023 年 1 月**&#x200B;将成为所有用户的默认体验。当前页面将被弃用，每个人都将必须使用新体验。 |
| **[!UICONTROL 异常检测]自动运行条件** | 2022 年 9 月 29 日 | 现在对时间序列自由格式表的所有列都自动运行[!UICONTROL 异常检测]。为了确保有数据可用于分析并加快项目加载，Adobe 将更改异常检测自动运行的方式。从 **2022 年 10 月 26 日**&#x200B;起，将对表中的第一个指标列自动运行[!UICONTROL 异常检测]。如果需要，可配置列设置以对其他列运行异常检测。 |
| **更新到新的 NetAcuity 网络运营商数据库** | 2022 年 9 月 26 日 | 原计划于 2022 年 10 月 5 日进行的本次更新已推迟到 **2023 年 1 月**。存储在 Adobe Analytics Data Warehouse 和 Analytics 数据馈送的 `carrier` 字段中的与运营商相关的信息将发生变化。过去，该列中的数据格式一直是 `<domain>:<ISP>`。Adobe 维护有内部查找表将这些 `<domain>:<ISP>` 值映射到运营商名称中，以便在 Adobe Analytics 报告工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream 等）中进行报告。查找文件 (`carrier.tsv`) 也随数据馈送一起提供，以便您能使用相同的映射。<p>此更新通过使用 NetAcuity 提供的更为准确的运营商数据库来增强运营商映射。 数据馈送中运营商列中的数据格式将继续更改。 与 `<domain>:<ISP>` 不同，它将包含运营商名称。 Adobe 将继续使用查找表，以尽可能保持与过去报告的连续性。 Adobe 应用查找的报告工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream 等） 将受益于更精确的映射。 当 Adobe 采用新的数据库时，一些映射（尤其是国际域名和 ISP 的映射）将发生更大的变化。数据馈送运营商查找文件 (`carrier.tsv`) 将维护旧映射并添加新映射。<p>Analytics Source Connector 当前未映射运营商字段，因此运营商报告当前在 Experience Platform、CJA 等中不可用。因此，使用新的运营商数据库不会影响 Experience Platform 中基于 Analytics Source Connector 提供的数据的任何内容。 |
| **改进的 IP 到地理位置映射** | 2022 年 9 月 26 日 | 我们的 IP 查找供应商 Digital Element 正在升级到新的改进数据集 (NetAcuity Pulse)，用于 IP 到地理位置映射。Adobe Analytics 原计划于 2022 年 10 月采用此新数据集，但现在将于 **2023 年 1 月**&#x200B;采用。新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p>所有 Adobe Analytics 工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream、数据馈送等） 将自动利用新的改进映射。 数据馈送中的数据格式不会发生变化。 通过 Analytics Source Connector 提供的 CJA 数据也将自动利用新的映射。 |
| **SFTP 升级** | 2022 年 9 月 19 日 | 此前，Adobe 曾表示将于 2022 年 9 月升级其安全文件传输协议 (SFTP) 服务，以提高文件传输的安全性。Adobe 于 **2022 年 9 月 20 日**&#x200B;执行了此升级。进行此更改后，不再支持某些 SFTP 客户端配置。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hans)详述的更改一致。 |
| **暂停 Reports &amp; Analytics 中的计划报告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，Adobe 宣布弃用特定于计划报告的多项功能，为之前宣布的 Reports &amp; Analytics 生命周期结束做准备。这些功能包括计划新报告和新数据提取的能力。<p>为响应客户延期请求并简化从 Reports &amp; Analytics 的过渡，Adobe 已决定将这些功能的访问权限延长至 **2023 年 1 月 31 日**。请注意，报告和数据提取的到期窗口仍为九个月；除非重新激活计划，否则报告和数据提取交付将在此期限结束时暂停。<p>重申一下，这些功能将于 2023 年 1 月 31 日弃用。在此日期之前，您必须将计划报告迁移到 Adobe Analytics 中可供您使用的其他机制之一。如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **在 Report Builder 中暂停计划任务** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，作为性能和交付优化工作的一部分，Adobe 在 Report Builder 中推出了对计划任务的更改。这些更改包括取消预定交付“在发生 x 次后结束”的功能。为了响应一些客户要求更多时间来探索和实施替代方案的请求，Adobe 已决定在 **2023 年 1 月 31 日**&#x200B;之前有限地恢复此功能选项。<p>您可以继续计划每小时 Report Builder 任务，并在最多发生 99 次后结束这些任务。请注意，回滚仅适用于小时任务；对于所有其他交付间隔期（每天、每周、每月和每年），“在发生 x 次后结束”不可用。请注意，此选项将于 2023 年 1 月 31 日弃用。如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。 [了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## 终止通知

| EOL产品或功能 | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **终止使用[!UICONTROL 发布列表]功能** | 2022 年 9 月 29 日 | 作为终止使用 Reports and Analytics 的一部分，预计在 **2023 年 12 月**&#x200B;终止使用发布列表。您将无法创建新的发布列表或访问现有的发布列表以发送或安排 Analysis Workspace 项目。[了解详情](/help/admin/admin/publishing-list.md) |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。如果您有任何问题，请联系您的客户关怀代表以获取 Data Workbench 的替代解决方案。[了解详情](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans) |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.23.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。
