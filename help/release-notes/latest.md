---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e35e437a61b925625f6dc7fa2344406c5a66e5fe
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 53%

---

# 最新Adobe Analytics发行说明（2022年3月）

>[!IMPORTANT]
>
>以下内容包含预发行信息，可能会发生更改。

* 对于2022年2月版发行说明，请转至 [此处](/help/release-notes/2022.md).
* 了解 [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新。在 Experience League 上获取最新的自助文档、教程和课程。

## Adobe Analytics 中的新增功能 {#aa-features}

| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| 工作区中的注释 | 通过工作区中的注释，您可以有效地将上下文数据细微差别和洞察传达给您的组织。 [了解详情](/help/analyze/analysis-workspace/components/annotations/overview.md) | 2022年3月23日 |
| Adobe Analytics登陆页面更新 | 更新了工作区/Reports &amp; Analytics联合登陆页面，提高了可用性并简化了导航。 [了解详情](/help/analyze/landing.md) | 2022年3月23日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了在尝试访问Activity Map时导致错误的问题。 (AN-267177)

* 修复了用户资产传输失败的问题。 (AN-279813)

* 修复了A4T工作区面板的问题。 （AN-281594；AN-282418）

* 修复了某些用户无法访问Adobe Analytics的问题。 (AN-282776)

* 修复了一些新创建的报表包无法收集数据的问题。 （AN-283114、AN-283311）

* 修复了无法使用操作系统维度检测Win11的问题。 (AN-275569和AN-275727;AN-280335)

* 修复了数据馈送电子邮件发送不正确的问题。 （AN-280255；AN-282051）


### Adobe Analytics 中的其他修复

AN-256929;AN-270937;AN-272158;AN-275130;AN-277830;AN-278635;AN-279066;AN-279683;AN-279899;AN-280504;AN-280617;AN-280663;AN-281423;AN-281608;AN-281671;AN-281963;AN-282027;AN-282218;AN-282605;AN-282632;AN-282654;AN-282694;AN-282744;AN-282756;AN-282804;AN-282862;AN-282903;AN-282937;AN-282892;AN-283315;AN-283338;AN-283388;AN-283417;AN-283474;AN-283511;AN-283691和AN-283957;

## Adobe Analytics管理员的重要注意事项

**更新日期： 2022年3月11日**

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 暂停旧计划报表 | 2022年3月11日 | 有效 **2022年4月15日**，则Adobe打算暂停创建日期超过两年（在2020年1月31日之前创建）的所有计划报表。 不会删除任何报表或数据。 只会暂停识别为两年以上的报表，并且不会发送其他计划报表。 [了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| 2022 年 ISO 区域更新 | 2021 年 3 月 11 日 | Adobe将在 **2022年6月10日**. 预计在这个版本之后将看到小规模更新。 |
| 更改Analytics处理通过Experience Edge收集的A4T数据的方式 | 2022 年 2 月 25 日 | 开 **2022年3月7日**，我们将更改处理通过Experience Edge发送到Adobe Analytics的一些与Target相关的数据的方式。 将Adobe Experience Platform Web SDK与Analytics和Target结合使用时，某些个性化事件会被计入 [!DNL Adobe Analytics] as [!UICONTROL 页面查看次数]. 这会导致页面查看计数虚增以及额外的服务器调用次数。 通过更改，将忽略不含Analytics内容的个性化调用。 包含A4T数据的个性化调用将记录A4T数据，但不会记录为可计费服务器调用，也不会影响页面查看次数或链接事件量度。 |
| 暂停旧的计划Report Builder任务 | 2022 年 2 月 24 日 | **2022年4月15日起生效**，则Adobe打算暂停两年前创建的所有计划Report Builder任务。 具体而言，此暂停适用于2020年1月31日之前创建的任何任务。 不会删除任务、工作簿或数据。 但是，将暂停识别为两年以上的任务，并且不会发送其他计划任务。 [了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| 旧版 Analytics OAuth/JWT 集成的允许列表 EOL 扩展到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和旧版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允许列表延长期将到期。此延长期为使用旧版 [!DNL Adobe Analytics] OAuth/JWT 凭据的客户提供额外的时间，以将其客户端集成迁移到 [Adobe IMS 凭据](https://developer.adobe.com/console)。该扩展到期会影响（但不限于）尚未完成必需的 IMS 迁移的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客户。如果客户目前正在通过允许列表扩展使用旧版 [!DNL Analytics] OAuth/JWT 凭据，但未在 2022 年 5 月 25 日之前完成向 IMS 凭据迁移，则将失去对 Adobe 服务的访问权限。Livestream 客户可以参考这些关于将客户端应用程序迁移到 IMS 凭据的[说明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。[!DNL Campaign] 客户可以联系他们的 Adobe 帐户团队，了解如何升级到最新版本的 [!DNL Campaign]。 |
| 安全文件传输协议 (SFTP) 服务升级 | 2022 年 3 月 3 日 | 在 **2022 年 5 月 15 日**，[!DNL Adobe Analytics] 将升级安全文件传输协议 (SFTP) 服务，以提高文件传输的安全性。作出此更改后，将不再支持某些 SFTP 客户端配置。我们还将增加一些在 **2022 年 3 月 1 日**&#x200B;之前可用的连接选项。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)详述的更改一致。 |
| EOL for [!DNL Reports & Analytics] | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)解释了生命周期结束的过程。 |

## AppMeasurement {#appm}

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
