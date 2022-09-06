---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: fe00b4d51d7bbfecf12c351530729e144088e248
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 86%

---

# 当前 Adobe Analytics 发行说明（2022 年 8 月）

**上次更新**:2022年9月6日

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新

## Adobe Analytics 的新增或更新功能

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| 在用于 Edge Collection 的 XDM 中支持列表变量 | 使客户能够通过 Experience Edge/Web SDK 收集数据，以使用 XDM 指定列表变量内容。 [了解详情](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/list.html?lang=zh-Hans#list-variables-using-the-web-sdk) | 2022 年 8 月 18 日 |
| 设置产品字符串变量时在用于 Edge Collection 的 XDM 中使用 SKU 字段 | 使客户能够通过 Experience Edge/Web SDK 收集数据，以使用 SKU 值设置产品变量中的产品字段。 [了解详情](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=zh-Hans#products-using-the-web-sdk) | 2022 年 8 月 18 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了几个数据馈送相关问题。 (AN-297264, AN-297295, AN-297449)

**适用于单个客户的修复**：

AN-274281、AN-280956、AN-285670、AN-288176、AN-289221、AN-289665、AN-289768、AN-294632、AN-294970、AN-295078、AN-295233、AN-295482、AN-295549、AN-295633、AN-295712、AN-295749、AN-295963、AN-295977、AN-296094、AN-296153、AN-296167、AN-296177、AN-296297、AN-296383、AN-296394、AN-296414、AN-296431、AN-296459、AN-296486、AN-296510、AN-296514、AN-296540、AN-296734、AN-296840、AN-296841、AN-296977、AN-296987、AN-297002、AN-297141、AN-297158、AN-297267、AN-297396、AN-297397、AN-297522、AN-297704、AN-297705、AN-297829、AN-297895；

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **EOL forData Workbench** | 2022年9月6日 | Adobe打算终止有效的生命周期Data Workbench **2023年12月31日**. 更多细节将很快传达。 |
| **SFTP 升级** | 2022年9月6日 | 以前，我们曾通知Adobe将在2022年9月升级其安全文件传输协议(SFTP)服务，以提高文件传输的安全性。 我们已将此升级推迟到 **待定**. 完成此更改后，将不再支持某些 SFTP 客户端配置。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hans)详述的更改一致。 |
| **由于 Google 客户端提示而更新设备查找** | 2022 年 8 月 19 日 | 开始于 **2022年10月**，当从Chromium浏览器(如Google Chrome和Microsoft Edge)获取点击的特定设备信息时，除了用户代理之外，Adobe还将开始使用客户端提示。 这是对Google逐步减少用户代理字符串中提供的信息，而不是通过客户端提示传递的数据的计划的响应。 在[此处](https://web.dev/user-agent-client-hints/)详细了解客户端提示。<p> 10 月之前，AppMeasurement 和 Web SDK 集合库都将支持收集客户端提示，并配置是否收集高熵客户端提示。作为此更改的一部分，Adobe 将使用 Device Atlas 进行与用户代理相关的所有设备查找。目前，Device Atlas 仅用于移动点击。这些更新可能会导致从用户代理派生的设备历史信息发生微小变化——特别是浏览器、浏览器类型、操作系统、操作系统类型和移动设备。 |
| **更新到新的 NetAcuity 运营商数据库** | 2022 年 7 月 11 日 | **从 2022 年 10 月开始**，Adobe Analytics Data Warehouse 和 Analytics 数据馈送中存储在 `carrier` 字段中的运营商相关信息将更改。 过去，该列中的数据格式一直是 `<domain>:<ISP>`。 Adobe 维护有内部查找表将这些 `<domain>:<ISP>` 值映射到运营商名称中，以便在 Adobe Analytics 报告工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream 等）中进行报告。 查找文件 (`carrier.tsv`) 也随数据馈送一起提供，以便您能使用相同的映射。<p>此更新通过使用 NetAcuity 提供的更为准确的运营商数据库来增强运营商映射。 数据馈送中运营商列中的数据格式将继续更改。 于 `<domain>:<ISP>` 不同，它将包含运营商名称。 Adobe 将继续使用查找表，以尽可能保持与过去报告的连续性。 Adobe 应用查找的报告工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream 等） 将受益于更精确的映射。 当我们采用新的数据库时，一些映射（尤其是国际域名和 ISP 的映射）将发生更大的变化。 数据馈送运营商查找文件 (`carrier.tsv`) 将维护旧映射并添加新映射。<p>Analytics Source Connector 当前未映射运营商字段，因此运营商报告当前在 AEP、CJA 等中不可用。 因此，使用新的运营商数据库不会影响 AEP 中基于 Analytics Source Connector 提供的数据的任何内容。 |
| **改进的 IP 到地理位置映射** | 2022 年 7 月 11 日 | 我们的 IP 查找供应商 Digital Element 正在升级到一个新的改进数据集 (NetAcuity Pulse)，用于 IP 到地理位置映射。 Adobe Analytics 将在 **2022 年 10 月**&#x200B;采用此新数据集。 新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p>所有 Adobe Analytics 工具（Analysis Workspace、Reports &amp; Analytics、报告 API、Data Warehouse、LiveStream、数据馈送等） 将自动利用新的改进映射。 数据馈送中的数据格式不会发生变化。 通过 Analytics Source Connector 提供的 CJA 数据也将自动利用新的映射。 |
| **暂停 Reports &amp; Analytics 中的计划报告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，我们宣布弃用计划报告的多项功能，为之前宣布的 Reports &amp; Analytics 生命周期结束做准备。这些功能包括计划新报告和新数据提取的能力。<p>为响应客户延期请求并简化从 Reports and Analytics 的过渡，我们决定将这些功能的访问权限延长至 **2023 年 1 月 31 日**。 请注意，报告和数据提取的到期窗口仍为九个月；除非重新激活计划，否则报告和数据提取交付将在此期限结束时暂停。<p>重申一下，这些功能将于 2023 年 1 月 31 日弃用。在此日期之前，您必须将计划报告迁移到 Adobe Analytics 中可供您使用的其他机制之一。如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **在 Report Builder 中暂停计划任务** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，作为性能和交付优化工作的一部分，我们在 Report Builder 中推出了对计划任务的更改。这些更改包括删除使计划投放“在x次发生后结束”的功能。 为了响应一些客户要求更多时间来探索和实施替代方案的请求，我们决定在 **2023 年 1 月 31 日**&#x200B;之前有限地恢复此功能选项。<p>您可以计划每小时 Report Builder 任务，并在最多发生 99 次后结束这些任务。请注意，回滚仅适用于每小时任务；“x次出现后结束”将不可用于所有其他提交间隔（每日、每周、每月和每年）。 请注意，此选项将于 2023 年 1 月 31 日弃用。如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。 [了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。报表、可视化图表和基础技术 [!DNL Reports & Analytics] 不再满足Adobe的技术标准。 大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)阐明生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

