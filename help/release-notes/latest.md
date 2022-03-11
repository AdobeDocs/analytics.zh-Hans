---
title: 最新的 Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1349dd63fcf1cc94e848f3c3af55af5f39b11f43
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 72%

---

# 当前的 Adobe Analytics 发行说明（2022 年 2 月）

**上次更新**:2022年3月11日

了解 [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新。在 Experience League 上获取最新的自助文档、教程和课程。

## Adobe Analytics 中的新增功能 {#aa-features}

| 功能 | 描述 | [目标日期](releases.md) |
| ----------- | ---------- | ------- |
| 移动记分卡项目预览模式 | 直接从记分卡生成器中预览您的移动记分卡在 Analytics 功能板应用程序中的外观。预览模式允许用户以与在该应用程序中相同的方式与过滤器和图表进行交互，使用户可以在保存和共享记分卡之前预览体验。用户还可以在预览模式下使用设备选择器来查看自己的记分卡在不同设备上的外观。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=en#preview) | 2022 年 2 月 16 日 |
| API项目端点 | 使用API添加、编辑或删除Analysis Workspace项目。 [了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | 2022年2月1日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了[!UICONTROL 服务器调用使用情况]的一些问题。（AN-279134、AN-279878、AN-280802、AN-279097、AN-191284、AN-269720）
* 修复了导致 Data Warehouse 导出空 .csv 文件的问题。(AN-280291)
* 修复了一个问题，该问题导致没有为最近的区段填充“受众名称”。(AN-279715)
* 修复了报告时间缓慢的问题。(AN-280055)
* 修复了“分类”功能未对所有维度项目进行分类的问题。(AN-280031)

### Adobe Analytics 中的其他修复

AN-268093、AN-273820、AN-274435、AN-274904、AN-275356、AN-275947、AN-276160、AN-276258、AN-276705、AN-277051、AN-277957、AN-278693、AN-278882、AN-279000、AN-279046、AN-279362、AN-279460、AN-279488、AN-279554、AN-279572、AN-279663、AN-279755、AN-279825、AN-280002、AN-280013、AN-280019、AN-280033、AN-280086、AN-280232、AN-280264、AN-280288、AN-280342、AN-280347、AN-280360、AN-280370、AN-280724、AN-280830、AN-280941、AN-281353、AN-281424、AN-281533

## [!DNL Analytics] 管理员的重要注意事项

**更新日期： 2022年3月11日**

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 暂停旧的计划报表 | 2022年3月11日 | 有效 **2022年4月15日**，则Adobe打算暂停创建日期超过两年（在2020年1月31日之前创建）的所有计划报表。 不会删除任何报表或数据。 只会暂停识别为两年以上的报表，并且不会发送其他计划报表。 [了解详情](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| 2022 年 ISO 区域更新 | 2021 年 3 月 11 日 | Adobe将在 **2022年6月10日**. 预计在这个版本之后将看到小规模更新。 |
| 更改Analytics处理通过Experience Edge收集的A4T数据的方式 | 2022 年 2 月 25 日 | 开 **2022年3月7日**，我们将更改处理通过Experience Edge发送到Adobe Analytics的一些与Target相关的数据的方式。 将Adobe Experience Platform Web SDK与Analytics和Target结合使用时，某些个性化事件会被计入 [!DNL Adobe Analytics] as [!UICONTROL 页面查看次数]. 这会导致页面查看计数虚增以及额外的服务器调用次数。 通过更改，将忽略不含Analytics内容的个性化调用。 包含A4T数据的个性化调用将记录A4T数据，但不会记录为可计费服务器调用，也不会影响页面查看次数或链接事件量度。 |
| 暂停旧的计划Report Builder任务 | 2022 年 2 月 24 日 | **2022年4月15日起生效**，则Adobe打算暂停两年前创建的所有计划Report Builder任务。 具体而言，此暂停适用于2020年1月31日之前创建的任何任务。 不会删除任务、工作簿或数据。 但是，将暂停识别为两年以上的任务，并且不会发送其他计划任务。 [了解详情](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| 旧版 Analytics OAuth/JWT 集成的允许列表 EOL 扩展到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和旧版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允许列表延长期将到期。此延长期为使用旧版 [!DNL Adobe Analytics] OAuth/JWT 凭据的客户提供额外的时间，以将其客户端集成迁移到 [Adobe IMS 凭据](https://developer.adobe.com/console)。该扩展到期会影响（但不限于）尚未完成必需的 IMS 迁移的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客户。如果客户目前正在通过允许列表扩展使用旧版 [!DNL Analytics] OAuth/JWT 凭据，但未在 2022 年 5 月 25 日之前完成向 IMS 凭据迁移，则将失去对 Adobe 服务的访问权限。Livestream 客户可以参考这些关于将客户端应用程序迁移到 IMS 凭据的[说明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。[!DNL Campaign] 客户可以联系他们的 Adobe 帐户团队，了解如何升级到最新版本的 [!DNL Campaign]。 |
| EOL for [!DNL Reports & Analytics] | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)解释了生命周期结束的过程。 |
| 安全文件传输协议 (SFTP) 服务升级 | 2022 年 3 月 3 日 | 在 **2022 年 5 月 15 日**，[!DNL Adobe Analytics] 将升级安全文件传输协议 (SFTP) 服务，以提高文件传输的安全性。作出此更改后，将不再支持某些 SFTP 客户端配置。我们还将增加一些在 **2022 年 3 月 1 日**&#x200B;之前可用的连接选项。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据，而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与[此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)详述的更改一致。 |

## AppMeasurement {#appm}

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
