---
title: 查看当前Adobe Analytics发行说明
description: 最新Analytics发行说明
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 44bbcabf0bdc74b560a650ce1892a52b4d98052c
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 61%

---

# 最新Adobe Analytics发行说明（2022年2月）

>[!IMPORTANT]
>
>这些发行说明包含可能发生更改的预发行信息。

**上次更新**:2022年2月10日

了解 [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新。在 Experience League 上获取最新的自助文档、教程和课程。

## Adobe Analytics 中的新增功能 {#aa-features}

| 功能 | 描述 | [目标日期](https://experienceleague.adobe.com/docs/analytics/technotes/releases.html?lang=zh-Hans) |
| ----------- | ---------- | ------- |
| 移动记分卡项目预览模式 | 直接从记分卡生成器中启动在Analytics功能板应用程序中显示移动记分卡的预览。 预览模式允许用户与过滤器和图表进行交互，其方式与应用程序中的过滤器和图表相同，允许用户在保存和共享记分卡之前预览体验。 用户还可以在预览模式下使用设备选取器，以查看其记分卡在不同设备上的显示效果。 | 2022 年 2 月 16 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了 [!UICONTROL 服务器调用使用情况]. （AN-279134、AN-279878、AN-280802、AN-279097、AN-191284、AN-269720）
* 修复了导致Data warehouse导出空.csv文件的问题。 (AN-280291)
* 修复了导致最近的区段无法填充受众名称的问题。 (AN-279715)
* 修复了报告时间缓慢的问题。 (AN-280055)
* 修复了分类未对所有维度项目进行分类的问题。 (AN-280031)


### Adobe Analytics 中的其他修复

AN-268093、AN-273820、AN-274435、AN-274904、AN-276160、AN-276258、AN-276705、AN-277051、AN-277957、AN-278693-、AN-AN-AN-AN-AN-AN-AN-AN-AN-AN、AN-AN-AN-AN、AN-AN-AN-AN-AN-AN-AN-AN、、AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-A-AN-AN-AN-A-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-An-AN-A


## [!DNL Analytics] 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 旧版 Analytics OAuth/JWT 集成的允许列表 EOL 扩展到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和旧版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允许列表延长期将到期。此延长期为使用旧版 [!DNL Adobe Analytics] OAuth/JWT 凭据的客户提供额外的时间，以将其客户端集成迁移到 [Adobe IMS 凭据](https://developer.adobe.com/console)。该扩展到期会影响（但不限于）尚未完成必需的 IMS 迁移的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客户。如果客户目前正在通过允许列表扩展使用旧版 [!DNL Analytics] OAuth/JWT 凭据，但未在 2022 年 5 月 25 日之前完成向 IMS 凭据迁移，则将失去对 Adobe 服务的访问权限。Livestream 客户可以参考这些关于将客户端应用程序迁移到 IMS 凭据的[说明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。[!DNL Campaign] 客户可以联系他们的 Adobe 帐户团队，了解如何升级到最新版本的 [!DNL Campaign]。 |
| EOL for [!DNL Reports & Analytics] | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 及其随附的报表和功能。[!DNL Reports & Analytics]支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知解释了生命周期结束的过程。](https://spark.adobe.com/page/6WnF8JK6IRDhf/) |
| 安全文件传输协议 (SFTP) 服务升级 | 2022 年 1 月 13 日 | 在 **2022 年 5 月 2 日**，[!DNL Adobe Analytics] 将升级安全文件传输协议 (SFTP) 服务，以提高文件传输的安全性。作出此更改后，将不再支持某些 SFTP 客户端配置。我们还将增加一些在 **2022 年 3 月 1 日**&#x200B;之前可用的连接选项。这仅会影响使用SFTP发送到Adobe Analytics或从Analytics检索到的数据。 FTP协议不会受到影响。 为避免服务中断，请确保您的SFTP客户端（代码、工具、服务）符合详细更改 [此处](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |

## AppMeasurement {#appm}

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)

