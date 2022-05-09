---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 43869c683ca30c94157c6822b53f02a917f6e3ff
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 95%

---

# 当前 Adobe Analytics 发行说明（2022 年 4 月）

**上次更新**:2022年5月9日

## 相关资源

* [以前的 2022 年发行说明](/help/release-notes/2022.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新

## Adobe Analytics 中的新增功能

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| Adobe Analytics 登陆页面更新 | 更新联合工作区/Reports &amp; Analytics 登录页面，提高可用性和导航的便利性。[了解详情](/help/analyze/landing.md) | 2022 年 4 月 20 日 |
| [!UICONTROL 下一个项目]或[!UICONTROL 上一个项目]工作区面板 | [!UICONTROL 下一个或上一个项目]面板允许您浏览您选择的维度项目之后或之前的项目。例如，如果您想查看特定产品页面、营销渠道甚至设备类型的下一个或上一个页面，请使用它。此面板不仅涉及传统的下一/上一报表，因为它允许您查看任何维度，并且不需要任何新实施即可获得见解。[了解详情](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 2022 年 4 月 20 日 |
| [!UICONTROL 页面摘要]工作区面板 | [!UICONTROL 页面摘要]面板为您选择的页面提供深入分析。它提供与旧版 Reports &amp; Analytics [!UICONTROL 页面摘要]报表相同的详细信息，外加更多信息。[了解详情](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 2022 年 4 月 20 日 |
| 取消了将 `x-proxy-global-company-id` 标头用于 2.0 API 调用的要求 | Adobe Analytics 2.0 API 不再需要 `x-proxy-global-company-id` 标头，因为此信息是端点 URL 的一部分。仍可包括此标头，但即使缺少它，也不再显示一条错误。 | 2022 年 4 月 20 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了数据源中的一个问题，即从数据源 UI 创建数据源时，保存数据源后，开始和结束日期会自动更改。日期自动更新了 1 天。(AN-281262)
* 修复了阻止通过电子邮件链接续订计划项目的问题。(AN-283622)
* 解决了一个问题，该问题导致在 Adobe 的浏览器类型查找表中无法识别近期的 Apple Safari 和 Microsoft Edge 版本。与[更新浏览器版本](/help/components/dimensions/browser.md)时相似，对浏览器类型查找表的更新仅纠正今后的数据。在 4 月 20 日更新了浏览器版本的查找表，而在 4 月 28 日更新了浏览器类型的查找表。（AN-284872；AN-285753；AN-286257）

### Adobe Analytics 中的其他修复

AN-274486、AN-279258、AN-279995、AN-280918、AN-281423、AN-282084、AN-282435、AN-283508、AN-283517、AN-283706、AN-283762、AN-283921、AN-284195、AN-284663、AN-284573、AN-284721、AN-284790、AN-284867、AN-284870、AN-284872、AN-284884、AN-284914、AN-284930、AN-284933、AN-284967、AN-284970、AN-285187、AN-285328、AN-285337、AN-285375、AN-285447、AN-285724、AN-285753、AN-285761

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **SFTP升级** | 2022 年 5 月 9 日 | 以前，我们曾通知Adobe将在2022年5月升级其安全文件传输协议(SFTP)服务，以提高文件传输的安全性。 我们已将升级工作推迟到2022年夏。 发生此更改后，将不再支持某些SFTP客户端配置。 这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hans)详述的更改一致。 |
| **Cross-Device Analytics (CDA) 权利** | 2022 年 4 月 13 日 | 自&#x200B;**2022 年 5 月 1 日**&#x200B;起，将 [CDA](/help/components/cda/overview.md) 的任何新实施限制在每个客户最多三个报表包 ID (RSID)。 |
| **更改 Adobe Analytics 如何处理通过 Experience Edge 收集的 A4T 数据** | 2022 年 3 月 31 日 | 在 2022 年 3 月 7 日，Analytics 更改了它如何处理从 Experience Edge 发出的某些调用，这些调用包括要用于 Analytics for Target (A4T) 报表的 Target 内容。从 3 月 7 日开始，将修改所有带 A4T 报表内容的点击，以使其不被视为页面查看或链接事件。自&#x200B;**2022 年 3 月 31 日**&#x200B;起，逻辑更具选择性，以使标准的页面查看和点击事件不被修改。此后，被修改的事件仅限只有 A4T 内容的仅个性化调用。 |
| **更新某些客户支持的浏览器加密方法** | 2022 年 3 月 28 日 | Adobe 提供两种密码安全级别，以满足客户对第一方数据收集安全性的不同需求。在 **2022 年 6 月 23 日**，对于将其安全级别设置为“高”的客户不再支持某些 HTTPS 加密算法（也称为密码）。此操作意味着某些旧版操作系统无法再将数据发送到 Analytics，因为它们不支持新型加密方法。不影响使用默认“标准”密码安全设置的客户。已直接联系所有当前使用“高”设置的客户。可在此处找到受此更改影响的密码的详细列表。 |
| **暂停旧版计划报表** | 2022 年 4 月 12 日 | 从 **2022 年 4 月 20 日**&#x200B;起，Adobe 打算暂停所有其创建日期大于两年的计划报表（即 2020 年 1 月 31 日之前创建的计划报表）。不删除任何报告或数据。仅暂停确认为期限大于两年的报表，并且不发送其他计划报表。了解详情 |
| **2022 年 ISO 区域更新** | 2021 年 3 月 11 日 | Adobe 打算在 **2022 年 6 月 10 日**&#x200B;执行 2022 年 ISO 区域更新。预计在此次发布后将看到少量地理信息更新。 |
| **暂停旧版计划 Report Builder 任务** | 2022 年 4 月 12 日 | 从 **2022 年 4 月 20 日**&#x200B;起，Adobe 打算暂停所有在大于两年之前创建的计划 Report Builder 任务。具体而言，这一暂停适用于 2020 年 1 月 31 日之前创建的任何任务。不删除任何任务、工作簿或数据。但是，仅暂停确认为期限大于两年的任务，并且不发送其他计划任务。了解详情 |
| **旧版 Analytics OAuth/JWT 集成的允许列表 EOL 延期已到期** | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和旧版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允许列表延期到期。此延长期为使用旧版 [!DNL Adobe Analytics] OAuth/JWT 凭据的客户提供额外的时间，以将其客户端集成迁移到 [Adobe IMS 凭据](https://developer.adobe.com/console)。此到期影响（但不限于）尚未完成其所需 IMS 迁移的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客户。当前正在通过允许列表延期使用旧版 [!DNL Analytics] OAuth/JWT 凭据，并且到 2022 年 5 月 25 日前未完成迁移到 IMS 凭据的用户将无法访问 Adobe 服务。Livestream 客户可以参考这些关于将客户端应用程序迁移到 IMS 凭据的[说明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。[!DNL Campaign] 客户可以联系他们的 Adobe 帐户团队，了解如何升级到最新版本的 [!DNL Campaign]。 |
| **[!DNL Reports & Analytics]** 的 EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)解释了生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
