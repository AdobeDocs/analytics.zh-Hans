---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 835898b2a4c060f2e0202d79c58c73d4928c330d
workflow-type: ht
source-wordcount: '1311'
ht-degree: 100%

---

# 当前 Adobe Analytics 发行说明（2022 年 9 月）

**上次更新日期**：2022 年 9 月 19 日

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新

## Adobe Analytics 的新增或更新功能

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| Workspace 中的组合图表可视化 | 通过组合图表，可在 Workspace 中更轻松且更直观地比较各种指标。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts.html) | 2022 年 9 月 14 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了导入和导出分类的问题。(AN-299267)

**个别客户的修复**：

AN-288519；AN-289300；AN-297387；AN-297465；AN-297520；AN-297641；AN-298134；AN-298351；AN-298429；AN-298483；AN-298520；AN-298582；AN-298816；AN-298832；AN-298855；AN-298864；AN-299407；AN-299545；AN-299644；AN-299715

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **SFTP 升级** | 2022 年 9 月 19 日 | 此前，Adobe 曾表示将于 2022 年 9 月升级其安全文件传输协议 (SFTP) 服务，以提高文件传输的安全性。Adobe 已将此次升级推迟至 **2022 年 9 月 20 日**。进行此更改后，不再支持某些 SFTP 客户端配置。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hans)详述的更改一致。 |
| **更改了 Analytics 如何处理通过 Experience Edge 收集的 A4T 数据** | 2022 年 9 月 14 日 | 2022 年 3 月，Analytics 更改了如何处理包括 A4T 数据的某些来自 Experience Edge 的调用。修改了带 A4T 报表内容的点击，以使其不被视为页面查看 (`t()`) 或链接跟踪 (`tl()`) 事件。此逻辑现已更新以包括其中未按预期修改 `propositionDisplay` 事件的情况。 |
| **Web SDK 中列表变量和列表属性的自动分隔符** | 2022 年 9 月 14 日 | 列表变量和列表属性现在使用报告包设置中指定的分隔符，除非在 XDM 中指定了分隔符覆盖。有关详细信息，请参阅[列表](/help/implement/vars/page-vars/list.md)变量。 |
| **Data Workbench 的生命周期结束日期** | 2022 年 9 月 14 日 | Adobe 打算在 **2023 年 12 月 31 日**&#x200B;结束 Data Workbench 的生命周期。如果您有任何问题，请联系您的客户关怀代表以获取 Data Workbench 的替代解决方案。 |
| **由于 Google 客户端提示而更新设备查找** | 2022 年 9 月 14 日 | 从 **2022 年 9 月 29 日**&#x200B;开始，根据来自 Chromium 浏览器（如 Google Chrome 和 Microsoft Edge）的点击得出某些设备信息时，除了使用用户代理之外，Adobe 还开始使用客户端提示。这是为了响应 Google 计划以逐步减少用户代理字符串提供的信息，替代通过客户端提示传递的数据。在[此处](https://web.dev/user-agent-client-hints/)详细了解客户端提示。<p> 10 月之前，AppMeasurement 和 Web SDK 集合库都将支持收集客户端提示，并配置是否收集高熵客户端提示。作为此更改的一部分，Adobe 将使用 Device Atlas 进行与用户代理相关的所有设备查找。目前，Device Atlas 仅用于移动点击。这些更新可能会导致从用户代理派生的设备历史信息发生微小变化——特别是浏览器、浏览器类型、操作系统、操作系统类型和移动设备。 |
| **更新到新的 NetAcuity 网络运营商数据库** | 2022 年 9 月 14 日 | **从 2022 年 10 月 5 日开始**，存储在 Adobe Analytics Data Warehouse 和 Analytics 数据馈送中的 `carrier` 字段中的与网络运营商相关的信息将变更。过去，该列中的数据格式一直是 `<domain>:<ISP>`。Adobe 维护有内部查找表将这些 `<domain>:<ISP>` 值映射到运营商名称中，以便在 Adobe Analytics 报告工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream 等）中进行报告。查找文件 (`carrier.tsv`) 也随数据馈送一起提供，以便您能使用相同的映射。<p>此更新通过使用 NetAcuity 提供的更为准确的运营商数据库来增强运营商映射。 数据馈送中运营商列中的数据格式将继续更改。 于 `<domain>:<ISP>` 不同，它将包含运营商名称。 Adobe 将继续使用查找表，以尽可能保持与过去报告的连续性。 Adobe 应用查找的报告工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream 等） 将受益于更精确的映射。 当 Adobe 采用新的数据库时，一些映射（尤其是国际域名和 ISP 的映射）将发生更大的变化。数据馈送运营商查找文件 (`carrier.tsv`) 将维护旧映射并添加新映射。<p>Analytics Source Connector 当前未映射运营商字段，因此运营商报告当前在 Experience Platform、CJA 等中不可用。因此，使用新的运营商数据库不会影响 Experience Platform 中基于 Analytics Source Connector 提供的数据的任何内容。 |
| **改进的 IP 到地理位置映射** | 2022 年 9 月 14 日 | 我们的 IP 查找供应商 Digital Element 用于 IP 到地理位置映射的数据集正在升级到一个经过改进的新数据集 (NetAcuity Pulse)。Adobe Analytics 将从 **2022 年 10 月 5 日**&#x200B;开始采用这个新的数据集。新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p>所有 Adobe Analytics 工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream、数据馈送等） 将自动利用新的改进映射。 数据馈送中的数据格式不会发生变化。 通过 Analytics Source Connector 提供的 CJA 数据也将自动利用新的映射。 |
| **暂停 Reports &amp; Analytics 中的计划报告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，Adobe 宣布弃用特定于计划报告的多项功能，为之前宣布的 Reports &amp; Analytics 生命周期结束做准备。这些功能包括计划新报告和新数据提取的能力。<p>为响应客户延期请求并简化从 Reports &amp; Analytics 的过渡，Adobe 已决定将这些功能的访问权限延长至 **2023 年 1 月 31 日**。请注意，报告和数据提取的到期窗口仍为九个月；除非重新激活计划，否则报告和数据提取交付将在此期限结束时暂停。<p>重申一下，这些功能将于 2023 年 1 月 31 日弃用。在此日期之前，您必须将计划报告迁移到 Adobe Analytics 中可供您使用的其他机制之一。如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **在 Report Builder 中暂停计划任务** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，作为性能和交付优化工作的一部分，Adobe 在 Report Builder 中推出了对计划任务的更改。这些更改包括取消预定交付“在发生 x 次后结束”的功能。为了响应一些客户要求更多时间来探索和实施替代方案的请求，Adobe 已决定在 **2023 年 1 月 31 日**&#x200B;之前有限地恢复此功能选项。<p>您可以继续计划每小时 Report Builder 任务，并在最多发生 99 次后结束这些任务。请注意，回滚仅适用于小时任务；对于所有其他交付间隔期（每天、每周、每月和每年），“在发生 x 次后结束”不可用。请注意，此选项将于 2023 年 1 月 31 日弃用。如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。 [了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。
