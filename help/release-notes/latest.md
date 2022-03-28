---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 533c323b8be651eca14a88641aa4a82705305297
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 77%

---

# 当前的 Adobe Analytics 发行说明（2022 年 3 月）

**上次更新日期：2022 年 3 月 28 日**

* 有关 2022 年 2 月版发行说明，请转到 [此处](/help/release-notes/2022.md)。
* 了解 [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新。在 Experience League 上获取最新的自助文档、教程和课程。

## Adobe Analytics 中的新增功能 {#aa-features}

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| 工作区注释 | 工作区注释使您能够有效地将上下文数据的细微差别和见解传达给您的组织。[了解详情](/help/analyze/analysis-workspace/components/annotations/overview.md) | 2022年3月23日开始逐步推出。 正式发布：2022年4月11日 |
| 全新 Adobe Analytics 登陆页面 | 对工作区/Reports &amp; Analytics联合登陆页面进行了更新，提高了可用性和导航方便性。 [了解详情](/help/analyze/landing.md) | 2022 年 4 月 1 日 |
| [!UICONTROL 下一项] 或 [!UICONTROL 上一项目] 工作区面板 | 的 [!UICONTROL 下一项或上一项] 面板允许您浏览所选维度项目之后或之前的项目。 例如，如果您想要查看特定产品页面、营销渠道，甚至设备类型的下一页或上一页，请使用它。 此面板不仅适用于旧版的下一个/上一个报表，因为它允许您查看任何维度，并且不需要任何新实施即可获得洞察。 | 2022 年 4 月 1 日 |
| [!UICONTROL 页面摘要] 工作区面板 | 的 [!UICONTROL 页面摘要] 面板为您选择的页面提供了深入分析。 它提供的详细信息与旧版Reports &amp; Analytics相同 [!UICONTROL 页面摘要] 报告，以及更多内容。 | 2022 年 4 月 1 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了在尝试访问 Activity Map 时导致错误的问题。(AN-267177)
* 修复了用户资源迁移失败的问题。(AN-279813)
* 修复了 A4T 工作区面板的问题。（AN-281594；AN-282418）
* 修复了一些用户无法访问 Adobe Analytics 的问题。(AN-282776)
* 修复了一些新创建的报表包未收集数据的问题。（AN-283114、AN-283311）
* 修复了错误发送数据馈送电子邮件的问题。（AN-280255；AN-282051）


### Adobe Analytics 中的其他修复

AN-256929；AN-270937；AN-272158；AN-275130；AN-277830；AN-278635；AN-279066；AN-279683；AN-279899；AN-280504；AN-280617；AN-280663；AN-281423；AN-281523；AN-281608；AN-281671；AN-281963；AN-282027；AN-282218；AN-282593；AN-282605；AN-282632；AN-282654；AN-282694；AN-282744；AN-282756；AN-282804；AN-282838；AN-282862；AN-282903；AN-282937；AN-282892；AN-283315；AN-283338；AN-283388；AN-283417；AN-283474；AN-283511；AN-283691、AN-283895；AN-283943；AN-283957；AN-284030；AN-284100；AN-284142；AN-284162

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 更新了某些客户支持的浏览器加密方法 | 2022 年 28 月 3 日 | Adobe提供两个密码安全级别，以满足客户对第一方数据收集安全性的不同需求。 开 **2022年6月23日** 对于安全级别设置为“High”的客户，我们将删除对某些HTTPS加密算法（称为密码）的支持。 这意味着某些旧版操作系统将无法再将数据发送到Analytics，因为它们不支持现代加密方法。 使用默认“标准”密码安全设置的客户将不会受到影响。 已直接联系所有当前使用“高”设置的客户。 有关受此更改影响的密码的详细列表，请参阅 [此处](/help/technotes/rdc/encryption-algos.md). |
| 暂停旧版计划报告 | 2022 年 3 月 11 日 | 从 **2022 年 4 月 15 日**&#x200B;起，Adobe 打算暂停所有创建日期超过两年的计划报告（2020 年 1 月 31 日前创建的任何任务）。任何报告或数据都不会被删除。只有确认创建超过两年的报告才会暂停，并且不会发送额外的计划报告。[了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| 2022 年 ISO 区域更新 | 2021 年 3 月 11 日 | Adobe 将在&#x200B;**2022 年 6 月 10 日**&#x200B;执行 2022 年 ISO 区域更新。预计在这个版本之后将看到小规模更新。 |
| 改变 Analytics 处理 Experience Edge 收集的 A4T 数据的方式 | 2022 年 2 月 25 日 | 我们在 **2022 年 3 月 7 日**&#x200B;改变了如何处理通过 Experience Edge 发给 Adobe Analytics 的某些与 Target 相关的数据。在将 Adobe Experience Platform Web SDK 与 Analytics 和 Target 结合使用时，一些个性化事件被计入[!DNL Adobe Analytics][!UICONTROL 页面查看]。这导致页面查看量增加，并导致额外的服务器调用。经过该更改后，将忽略无 Analytics 内容的个性化调用。带有 A4T 数据的个性化调用将记录 A4T 数据，但不会记录为计费服务器调用，也不会影响页面查看或链接事件指标。 |
| 暂停旧版计划 Report Builder 任务 | 2022 年 2 月 24 日 | 从 **2022 年 4 月 15 日**&#x200B;起，Adobe 打算暂停所有创建日期超过两年的计划 Report Builder 任务。具体而言，这一暂停适用于 2020 年 1 月 31 日之前创建的任何任务。任何任务、工作簿或数据都不会被删除。但是，只有确认创建超过两年的任务才会暂停，并且不会发送其他计划任务。[了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| 旧版 Analytics OAuth/JWT 集成的允许列表 EOL 扩展到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和旧版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允许列表延长期将到期。此延长期为使用旧版 [!DNL Adobe Analytics] OAuth/JWT 凭据的客户提供额外的时间，以将其客户端集成迁移到 [Adobe IMS 凭据](https://developer.adobe.com/console)。该扩展到期会影响（但不限于）尚未完成必需的 IMS 迁移的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客户。如果客户目前正在通过允许列表扩展使用旧版 [!DNL Analytics] OAuth/JWT 凭据，但未在 2022 年 5 月 25 日之前完成向 IMS 凭据迁移，则将失去对 Adobe 服务的访问权限。Livestream 客户可以参考这些关于将客户端应用程序迁移到 IMS 凭据的[说明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。[!DNL Campaign] 客户可以联系他们的 Adobe 帐户团队，了解如何升级到最新版本的 [!DNL Campaign]。 |
| 安全文件传输协议 (SFTP) 服务升级 | 2022 年 3 月 3 日 | 在 **2022 年 5 月 15 日**，[!DNL Adobe Analytics] 将升级安全文件传输协议 (SFTP) 服务，以提高文件传输的安全性。作出此更改后，将不再支持某些 SFTP 客户端配置。我们还将增加一些在 **2022 年 3 月 1 日**&#x200B;之前可用的连接选项。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)详述的更改一致。 |
| EOL for [!DNL Reports & Analytics] | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)解释了生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
