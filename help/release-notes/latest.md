---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 93937279fa9d342048c7a16cabc50e92f95cf74d
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 74%

---

# 最新Adobe Analytics发行说明（2022年6月）

>[!NOTE]
>
>此页面包含预发行信息，这些信息可能会发生变化。

**上次更新时间**：2022 年 6 月 14 日

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新

## Adobe Analytics 中的新增功能

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| 新的流量可视化图表UI | 为流量可视化图表提供了额外的功能，使其更强大、更强大。 [了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=en) | 2022 年 6 月 15 日 |
| 在移动记分卡中共享注释 | 您可以在移动记分卡中显示在工作区中创建的注释。 这允许您直接在移动记分卡项目中共享与您的组织和促销活动有关的上下文数据细微差别和分析，这些项目可在Analytics功能板移动应用程序中查看。 [了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/mobile-annotations.html?lang=en) | 2022 年 6 月 15 日 |
| 支持带有边缘集合的促销变量的产品语法版本 | 您现在可以通过设置相关的XDM字段，使用产品语法的等效函数来设置推销变量。 查找有关促销变量产品语法的更多详细信息 [此处](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=zh-Hans). 请参阅产品语法的映射 [此处](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en#aep-edge). | 2022 年 6 月 15 日 |
| 通过 Experience Edge 填充生命周期维度和量度 | Analytics 报表中现在将显示通过 Experience Edge 发送的移动生命周期数据。有关哪些XDM字段映射到现有移动设备生命周期报表的详细信息，请参阅相关文档。 [了解详情](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 2022 年 5 月 27 日 |
| 新分类体验 — 第1阶段 | 这一新分类集用户体验的分阶段发布显着提高了对客户拥有分类数据的可见性。 GA估计于2023年初。 | 有限测试从2022年6月15日开始 |

{style=&quot;table-layout:auto&quot;}

### Adobe Analytics 中的修复

AN-251686、AN-283542、AN-286572、AN-286945、AN-286784、AN-286944、AN-287012、AN-287319、AN-287333、AN-287348、AN-287429、AN-288238、AN-288281、AN-288660、AN-288769、AN-288798、AN-288871、AN-288872、AN-288941、AN-288951、AN-288952、AN-288956、AN-289062、AN-289340、AN-289346、AN-289488、AN-289562、AN-289580、AN-289861、AN-289892;

### Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **暂停 Reports &amp; Analytics 中的计划报告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，我们宣布弃用计划报告的多项功能，为之前宣布的 Reports &amp; Analytics 生命周期结束做准备。这些功能包括计划新报告和新数据提取的能力。<p>为响应客户延期请求并简化从 Reports and Analytics 的过渡，我们决定将这些功能的访问权限延长至 **2023 年 1 月 31 日**。 请注意，报告和数据提取的到期窗口仍为九个月；除非重新激活计划，否则报告和数据提取交付将在此期限结束时暂停。<p>重申，这些功能将于2023年1月31日被弃用。 在此日期之前，您必须将计划报表迁移到Adobe Analytics中可用的其他机制之一。 如果还有其他问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **在 Report Builder 中暂停计划任务** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，作为性能和交付优化工作的一部分，我们在 Report Builder 中推出了对计划任务的更改。这些更改包括取消预定交付“在发生 x 次后结束”的功能。为了响应一些客户要求更多时间来探索和实施替代方案的请求，我们决定在 **2023 年 1 月 31 日**&#x200B;之前有限地恢复此选项。<p>您可以继续计划每小时Report Builder任务，并在最多99次发生后使任务结束。 请注意，回滚仅适用于小时任务；对于所有其他交付间隔期（每天、每周、每月和每年），“在发生 x 次后结束”不可用。请注意，此选项将于 2023 年 1 月 31 日弃用。如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。[了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP 升级** | 2022 年 5 月 9 日 | 之前，我们已告知 Adobe 将在 2022 年 5 月升级其安全文件传输协议 (SFTP) 服务以提高文件传输的安全性。我们已将此升级推迟到 **2022 年夏天**。完成此更改后，将不再支持某些 SFTP 客户端配置。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hans)详述的更改一致。 |
| **更新某些客户支持的浏览器加密方法** | 2022 年 3 月 28 日 | Adobe 提供两种密码安全级别，以满足客户对第一方数据收集安全性的不同需求。在 **2022 年 6 月 23 日**，对于将其安全级别设置为“高”的客户不再支持某些 HTTPS 加密算法（也称为密码）。此操作意味着某些旧版操作系统无法再将数据发送到 Analytics，因为它们不支持新型加密方法。不影响使用默认“标准”密码安全设置的客户。已直接联系所有当前正在使用“高”设置的客户。受此影响的密码的详细列表 |
| **2022 年 ISO 区域更新** | 2021 年 3 月 11 日 | Adobe在 **2022年6月10日**. 预计在此次发布后将看到少量地理信息更新。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)解释了生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

