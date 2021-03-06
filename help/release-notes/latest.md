---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 54%

---

# 最新Adobe Analytics发行说明（2022年7月）

**上次更新**:2022年7月13日

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新

## Adobe Analytics 中的新增功能

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| 在XDM中支持用于边缘收集的促销变量 | 允许客户通过Experience Edge/Web SDK收集数据，以使用XDM为促销变量(eVar)指定各种值。 [了解详情](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar-merchandising.html?lang=en) | 2022 年 6 月 29 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了一些区段转换错误。 （AN-291262、AN-294092）

**针对单个客户的修复**:

AN-280192;AN-281628;AN-287022;AN-287104;AN-287876;AN-288802;AN-288457;AN-288779;AN-288799;AN-289198;AN-289852;AN-289931;AN-290162;AN-290213;AN-291059;AN-291090;AN-291270;AN-294091;AN-294135;AN-294152;AN-294158;AN-294285;AN-294317;AN-294404;AN-294531;AN-294769;AN-294984;AN-295172;AN-295211;AN-295224;AN-295413;AN-295440;AN-295465;AN-295499;AN-295516;

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **系统生成电子邮件的新域** | 2022 年 7 月 13 日 | 开 **2022年5月18日**，则Adobe会从工作区项目、警报和超量警报中更改发件人的域名，该域名来自 `noreply@omniture.com` to `noreply@adobe.com`. 如果贵组织仅允许特定发件人，请将此新电子邮件添加到允许列表。 |
| **更新新的NetAcuity载体数据库** | 2022 年 7 月 11 日 | **自2022年10月起**，存储在 `carrier` “Adobe AnalyticsData warehouse”和“Analytics数据馈送”中的字段将发生更改。 以前，该列中的数据格式 `<domain>:<ISP>`. Adobe维护了一个内部查找表来映射这些 `<domain>:<ISP>` 值转换为运营商名称，以便在Adobe Analytics报表工具(Analysis Workspace、Reports &amp; Analytics、报表API、data warehouse、LiveStream等)中进行报告 查找文件(carrier.tsv)还提供了数据馈送，以便数据馈送客户可以使用相同的映射。<p>此更新通过使用NetAcuity中更准确的载波数据库来增强我们的载波映射。 数据馈送中运营商列中数据的格式将随之更改。 而不是 `<domain>:<ISP>`，则将包含运营商名称。 Adobe将继续使用查找表，以尽可能保持与过去报表的连续性。 Adobe应用查找的报表工具(Analysis Workspace、Reports &amp; Analytics、报表API、data warehouse、LiveStream等) 更准确的映射将使您受益。 当我们采用新数据库时，某些映射（特别是对于国际域和ISP）的变化会比其他映射更大。 数据馈送运营商查找文件(carrier.tsv)将维护旧映射并添加新映射。<p>Analytics源连接器当前未映射运营商字段，因此目前在AEP、CJA等中不提供运营商报表。 因此，使用新的运营商数据库不会影响AEP中任何基于Analytics源连接器提供数据的内容。 |
| **改进了IP到地理位置的映射** | 2022 年 7 月 11 日 | 我们的IP查找供应商Digital Element正在升级到新的改进数据集(NetAcuity Pulse)，以便进行IP到地理位置的映射。 Adobe Analytics将在 **2022年10月** 时间范围。 新数据库将比以前的版本更准确。 当采用新数据库时，某些IP到地理映射将发生更改/改进。<p>所有Adobe Analytics工具(Analysis Workspace、Reports &amp; Analytics、报表API、data warehouse、LiveStream、数据馈送等) 将自动利用新的改进映射。 数据馈送中的数据格式不会发生更改。 通过Analytics源连接器提供的CJA数据还将自动利用新映射。 |
| **暂停 Reports &amp; Analytics 中的计划报告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，我们宣布弃用计划报告的多项功能，为之前宣布的 Reports &amp; Analytics 生命周期结束做准备。这些功能包括计划新报告和新数据提取的能力。<p>为响应客户延期请求并简化从 Reports and Analytics 的过渡，我们决定将这些功能的访问权限延长至 **2023 年 1 月 31 日**。 请注意，报告和数据提取的到期窗口仍为九个月；除非重新激活计划，否则报告和数据提取交付将在此期限结束时暂停。<p>重申一下，这些功能将于 2023 年 1 月 31 日弃用。在此日期之前，您必须将计划报告迁移到 Adobe Analytics 中可供您使用的其他机制之一。如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **在 Report Builder 中暂停计划任务** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，作为性能和交付优化工作的一部分，我们在 Report Builder 中推出了对计划任务的更改。这些更改包括取消预定交付“在发生 x 次后结束”的功能。为了响应一些客户要求更多时间来探索和实施替代方案的请求，我们决定在 **2023 年 1 月 31 日**&#x200B;之前有限地恢复此选项。<p>您可以计划每小时 Report Builder 任务，并在最多发生 99 次后结束这些任务。请注意，回滚仅适用于小时任务；对于所有其他交付间隔期（每天、每周、每月和每年），“在发生 x 次后结束”不可用。请注意，此选项将于 2023 年 1 月 31 日弃用。如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP 升级** | 2022 年 5 月 9 日 | 之前，我们已告知 Adobe 将在 2022 年 5 月升级其安全文件传输协议 (SFTP) 服务以提高文件传输的安全性。我们已将此升级推迟到 **2022 年夏天**。完成此更改后，将不再支持某些 SFTP 客户端配置。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hans)详述的更改一致。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)解释了生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

