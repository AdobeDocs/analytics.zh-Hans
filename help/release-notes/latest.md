---
title: 最新的 Analytics 发行说明
description: 查看当前的 Adobe Analytics 发行说明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 614dff141e4201d09dc7e585e9f8744e4b37faf1
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 73%

---

# 最新Adobe Analytics发行说明（2022年4月）

**上次更新**:2022年4月13日

* 对于2022年3月版发行说明，请转至 [此处](/help/release-notes/2022.md).

* 有关Customer Journey Analytics发行说明，请转到 [此处](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans).

* 有关Media Analytics发行说明，请转到 [此处](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en).

* 了解 [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新。在 Experience League 上获取最新的自助文档、教程和课程。


| 功能 | 描述 | [预定日期](releases.md) |
| ----------- | ---------- | ------- |
| 全新 Adobe Analytics 登陆页面 | 更新联合工作区/Reports &amp; Analytics 登录页面，提高可用性和导航的便利性。[了解详情](/help/analyze/landing.md) | 2022 年 4 月 20 日 |
| [!UICONTROL 下一个项目]或[!UICONTROL 上一个项目]工作区面板 | [!UICONTROL 下一个或上一个项目]面板允许您浏览您选择的维度项目之后或之前的项目。例如，如果您想查看特定产品页面、营销渠道甚至设备类型的下一个或上一个页面，请使用它。该面板超越了传统的下一个/上一个报告，因为它允许您查看任何维度并且不需要任何新的实施来获得见解。 | 2022 年 4 月 20 日 |
| [!UICONTROL 页面摘要]工作区面板 | [!UICONTROL 页面摘要]面板为您选择的页面提供深入分析。它提供与旧版 Reports &amp; Analytics [!UICONTROL 页面摘要]报告相同以及更多信息。 | 2022 年 4 月 20 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修复

* 修复了数据馈送中的一个问题：从数据馈送UI创建数据馈送时，在保存数据馈送后，开始日期和结束日期会自动更改。 日期在1天前更新。 (AN-281262)

* 修复了通过电子邮件链接阻止续订计划项目的问题。 (AN-283622)

### Adobe Analytics 中的其他修复

AN-274486;AN-279258;AN-279995;AN-280918;AN-281423;AN-282084;AN-282435;AN-283508;AN-283517;AN-283706;AN-283762;AN-283921;AN-284195;AN-284663;AN-284573;AN-284721;AN-284790;AN-284867;AN-284870;AN-284872;AN-284884;AN-284914;AN-284930;AN-284933;AN-284967;AN-284970;AN-285187;AN-285328;AN-285337;AN-285375;AN-285447;AN-285724;AN-285753;AN-285761;

## Adobe Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 跨设备分析(CDA)权利 | 2022 年 4 月 13 日 | 有效 **2022年5月1日**，任何新实施 [CDA](/help/components/cda/overview.md) 将限制为每个客户最多三个报表包ID(RSID)。 |
| 更改了Adobe Analytics处理通过Experience Edge收集的A4T数据的方式 | 2022 年 3 月 31 日 | 2022年3月7日，我们更改了处理来自Experience Edge的一些调用的方式，这些调用包括适用于Analytics for Target(A4T)报表的Target内容。 从3月7日开始，已修改所有包含A4T报表内容的点击，以便不将其视为页面查看或链接事件。 开始 **2022年3月31日**，我们更改了逻辑，以便更加选择性，从而不会修改标准的页面查看和点击事件。 今后，将修改的唯一事件将是仅具有A4T内容的个性化调用。 |
| 更新某些客户支持的浏览器加密方法 | 2022 年 3 月 28 日 | Adobe 提供两种密码安全级别，以满足客户对第一方数据收集安全性的不同需求。在 **2022 年 6 月 23 日**，我们将为安全级别设置为“高”的客户移除对某些 HTTPS 加密算法（称为密码）的支持。这意味着一些较旧的操作系统将不再能够将数据发送到 Analytics，因为它们不支持现代加密方法。使用默认“标准”密码安全设置的客户不会受到影响。目前使用“高”设置的所有客户都已被直接联系。可在此处找到受此更改影响的密码的详细列表。 |
| 暂停旧版计划报告 | 2022 年 4 月 12 日 | 从 **2022 年 4 月 21 日**&#x200B;起，Adobe 打算暂停所有创建日期超过两年的计划报告（2020 年 1 月 31 日前创建的任何任务）。任何报告或数据都不会被删除。只有确认创建超过两年的报告才会暂停，并且不会发送额外的计划报告。了解详情 |
| 2022 年 ISO 区域更新 | 2021 年 3 月 11 日 | Adobe 将在&#x200B;**2022 年 6 月 10 日**&#x200B;执行 2022 年 ISO 区域更新。预计在此版本之后会看到较小的地理信息更新。 |
| 暂停旧版计划 Report Builder 任务 | 2022 年 4 月 12 日 | 有效 **2022年4月21日**，则Adobe打算暂停两年前创建的所有计划Report Builder任务。 具体而言，这一暂停适用于 2020 年 1 月 31 日之前创建的任何任务。任何任务、工作簿或数据都不会被删除。但是，只有确认创建超过两年的任务才会暂停，并且不会发送其他计划任务。了解详情 |
| 旧版 Analytics OAuth/JWT 集成的允许列表 EOL 扩展到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和旧版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允许列表延长期将到期。此延长期为使用旧版 [!DNL Adobe Analytics] OAuth/JWT 凭据的客户提供额外的时间，以将其客户端集成迁移到 [Adobe IMS 凭据](https://developer.adobe.com/console)。该扩展到期会影响（但不限于）尚未完成必需的 IMS 迁移的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客户。如果客户目前正在通过允许列表扩展使用旧版 [!DNL Analytics] OAuth/JWT 凭据，但未在 2022 年 5 月 25 日之前完成向 IMS 凭据迁移，则将失去对 Adobe 服务的访问权限。Livestream 客户可以参考这些关于将客户端应用程序迁移到 IMS 凭据的[说明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。[!DNL Campaign] 客户可以联系他们的 Adobe 帐户团队，了解如何升级到最新版本的 [!DNL Campaign]。 |
| EOL for [!DNL Reports & Analytics] | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 [!DNL Reports & Analytics] 及其随附的报告和功能。支持 [!DNL Reports & Analytics] 的报表、可视化图表和底层技术不再满足 Adobe 的技术标准。大部分 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 中都可用。自 2015 年发布 Analysis Workspace 以来，[!DNL Reports & Analytics] 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)解释了生命周期结束的过程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

有关 AppMeasurement 版本（版本 2.22.4）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
