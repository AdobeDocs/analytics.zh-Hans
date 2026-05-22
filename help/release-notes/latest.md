---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 1365
ht-degree: 60%

---

# 当前Adobe Analytics发行说明（2026年5月）

**上次更新日期**：2026年5月13日

这些发行说明涵盖2026年5月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **用于Adobe Analytics的MCP服务器** <br/>Analytics MCP（模型上下文协议）服务器允许您将受支持的MCP客户端连接到Adobe Analytics。 连接后，MCP客户端可以调用特定于产品的工具来检索数据、运行查询或执行作为LLM或代理工作流一部分的受支持操作。 有关详细信息，请参阅[Analytics MCP服务器](https://developer.adobe.com/analytics-mcp/docs/)。<p>如果您在Beta测试期间使用这些MCP服务器，请注意，Beta测试版和生产版端点之间有不同的URL。 请确保在5月31日之前将测试期间创建的任何代理工作流更新为使用生产端点。</p> | | 2026年5月5日 |
| Adobe Analytics中的&#x200B;**历程画布** <br/>历程画布是Analysis Workspace中的一个可视化图表，通过它可分析用户如何进入或退出历程，从而深入了解所定义的用户历程。 它允许您创建灵活的节点和箭头图，以表示历程中包含的事件、维度项和区段的任意组合。 当您将节点拖到画布上或重新排列历程的事件和条件时，数据会更新。<p>历程画布以前仅适用于Customer Journey Analytics。</p><p>要了解有关Adobe Analytics中历程画布的更多信息，请参阅[历程画布概述](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)。 </p><p>要了解如何在Adobe Analytics中构建历程画布可视化，请参阅[配置历程画布](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。</p> | 2026年5月18日 | 2026年6月5日 |
| **归因模型API报告指南** <br/>提供了新的Adobe Analytics 2.0 API归因模型报告指南。 该指南介绍了如何在Dimension API报表中包含归因模型对象数据。<p>有关详细信息，请参阅[Dimension API归因模型](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/attmodel)。</p> | | 2026年5月 |
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

**Activity Map**：
**Analysis Workspace**： AN-446522、AN-445779、AN-445759、AN-444676、AN-442813、AN-441943、AN-441717、AN-441538、AN-441123、AN-440976、AN-440952、AN-440919、AN-440599、AN-439797、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215、AN-、AN-、AN-
**分类**： AN-447743、AN-447296、AN-447130、AN-446552、AN-446324、AN-446040、AN-445841、AN-445753、AN-444992、AN-444979、AN-444428、AN-444332、AN-443507、AN-442906、AN-442232、AN-442207、AN-442133、AN-442035、AN-441901、AN-441807、AN-441671、AN-441333、AN-441302 AN-441267、AN-441132、AN-441085、AN-441048、AN-440846、AN-440727、AN-440716 440496 440429 432100
**数据馈送和Data Warehouse**：AN-447344、AN-446654、AN-445126、AN-444492、AN-442802、AN-442211、AN-442048、AN-441719、AN-441534、AN-441300、AN-441183、AN-441011、AN-440625
**迁移**： AN-442467、AN-440380、AN-440357
**导出**：
**Report Builder**： AN-448697、AN-447128、AN-441148、AN-441136、AN-438147、AN-425150
**报告**： AN-445123、AN-444869、AN-443453、AN-443275、AN-443148、AN-442464、AN-442148、AN-441811、AN-441506、AN-441149、AN-441119、AN-440545、AN-440511、AN-440300、AN-431409、AN-423359、AN-406242
**报表包**：
**计划报告**：
**分段**：
**Other**： AN-449159、AN-444661、AN-439429、AN-439423、AN-430988、AN-397985


## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **直播流处理改进** | 2026 年 1 月 14 日 | Adobe 计划对 LiveStream 负载的格式进行改进和更改。 这些更新提供了 LiveStream 与其他 Adobe Analytics 功能（如 Analysis Workspace）之间更好的对等性。 现在提供一个预览端点，您可以测试这些计划的更改。 有关完整的更改列表和预览端点详细信息，请参阅 [LiveStream 发行说明](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)。 Adobe 计划于 2026 年 4 月 13 日硬性切换到更新的负载格式。 |
| **TLS 1. 2 密码套件移除** | 2026 年 2 月 11 日 | 管理员须知：Adobe 计划于 2026 年 5 月 27 日从 Adobe 数据收集服务器中移除对以下 TLS 1.2 密码套件的支持。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>对于大多数实施都不需要客户进行任何操作。 此更改主要影响那些从旧版原生应用程序用过时 TLS 库发送的 Analytics 数据，以及少量的使用过时浏览器或操作系统的 Web 访客。 移除对这些密码套件的支持有助于增强安全性，使 Adobe 与现代加密标准保持一致。 目前，不到 0.1% 的数据收集流量使用这些密码套件。</p> |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。 所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。 新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。 它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。 要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。 新的 Report Builder 仅通过 Microsoft Store 作为插件提供。 许多组织要求在向用户提供加载项之前进行内部审批流程。 请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **通过旧域或旧 SSO 访问** | 2025年 4 月 10 日 | Adobe 计划更新用户访问 Adobe Analytics 的方式，以增强安全性并简化您的登录体验。 作为此项努力的一部分，通过旧域或旧 SSO（包括 `my.omniture.com`）进行的访问将于 **2026 年 1 月 2 日**&#x200B;永久停止。 此日期之后，旧版登录凭据和旧版 SSO 将不再起作用。 所有用户都必需通过 `experience.adobe.com` 使用他们的 Adobe Experience Cloud ID 登录。 如果您需要有关 Experience Cloud ID 方面的帮助，请联系您所在组织的 Adobe Analytics 管理员或 [Adobe 客户服务](https://helpx.adobe.com/cn/contact.html)。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [流媒体服务发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/release-notes/release-notes)
* [Adobe CX Enterprise产品的最新版本更新](https://business.adobe.com/products/adobe-experience-cloud-products.html)
