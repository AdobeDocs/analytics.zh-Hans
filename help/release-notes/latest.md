---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7a245e2c24e8763c93150aa5b9f3ac2d197f6f1f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 54%

---

# 当前 Adobe Analytics 发行说明（2026 年 4 月）

**上次更新时间**：2026年4月9日

这些发行说明涵盖2026年4月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **用于Adobe Analytics的MCP服务器** <br/>您现在可以使用MCP（模型上下文协议）将Adobe Analytics绑定到现有代理工作流中。 您可以使用自然语言请求报表和见解。<p>（文档链接见下文。）</p> | | 2026年4月底 |
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去实时流媒体内容的计划数据，以便更轻松准确地跟踪收视率。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |
| **其他API日期范围格式**<br/>&#x200B;现在支持使用两种新格式在Analytics 2.0 API报表请求中指定日期范围。 这包括日期公式和混合格式。 [了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | 2026 年 3 月 |
| **API报表请求中的可选维度**<br/>&#x200B;报表API请求中不需要维度对象。 如果未指定维度，则响应会显示总计报表的数据。 [了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | 2026 年 3 月 |
| **日期趋势高级API报告**<br/>&#x200B;新的Adobe Analytics 2.0 API日期趋势高级报告指南。 使用日期范围比较和区段创建高级日期趋势API报表。 [了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | 2026 年 3 月 |

## Adobe Analytics 中的修复

**Activity Map**：
**Analysis Workspace**： AN-442813、AN-442410、AN-441943、AN-441717、AN-434855、AN-431409、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215
**分类**：AN-443453、AN-443275、AN-443148、AN-442906、AN-442232、AN-442207、AN-442148、AN-442133、AN-441937、AN-441901、AN-441807、AN-441671、AN-441333、AN-441302、AN-441149、AN-441132、AN-441085、AN-441048、AN-440846、AN-440727、AN-440716、AN-440511、AN-440496 432100
**数据馈送和Data Warehouse**：AN-442211、AN-441719、AN-441183、AN-441011、AN-440625、AN-438953
**迁移**： AN-442467、AN-440380、AN-440357
**导出**：
**Report Builder**： AN-441136、AN-438147、AN-425150
**报告**： AN-441506、AN-440919、AN-440545、AN-440300
**报表包**： AN-439429、AN-439423、AN-430988
**计划报告**：
**分段**：
**Other**： AN-423359、AN-406242、AN-397985


## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **实时流处理改进** | 2026年1月14日 | Adobe计划对LiveStream有效负载的格式进行改进和更改。 这些更新在LiveStream与其他Adobe Analytics功能（如Analysis Workspace）之间提供了更好的对等性。 预览端点可用，可让您测试计划的更改。 有关更改完整列表和预览终结点详细信息，请参阅[LiveStream发行说明](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)。 Adobe计划在2026年4月13日硬性转换到更新的有效载荷格式。 |
| **TLS 1.2密码套件移除** | 2026年2月11日 | 管理员须知： Adobe计划于2026年5月27日从Adobe数据收集服务器中删除对以下TLS 1.2密码包的支持。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>大多数实施不需要客户操作。 此更改主要影响从使用过时TLS库的旧版本机应用程序发送的Analytics数据，以及少量使用过时浏览器或操作系统的Web访客。 取消对这些密码包的支持可增强安全性，并使Adobe与现代加密标准保持一致。 目前，不到0.1%的数据收集流量依赖这些密码套件。</p> |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。新的 Report Builder 仅通过 Microsoft Store 作为插件提供。许多组织要求在向用户提供加载项之前进行内部审批流程。请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **通过旧域或旧 SSO 访问** | 2025年 4 月 10 日 | Adobe 计划更新用户访问 Adobe Analytics 的方式，以增强安全性并简化您的登录体验。作为此项努力的一部分，通过旧域或旧 SSO（包括 `my.omniture.com`）进行的访问将于 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之后，旧版登录凭据和旧版 SSO 将不再起作用。所有用户都必需通过 `experience.adobe.com` 使用他们的 Adobe Experience Cloud ID 登录。如果您需要有关 Experience Cloud ID 方面的帮助，请联系您所在组织的 Adobe Analytics 管理员或 [Adobe 客户服务](https://helpx.adobe.com/cn/contact.html)。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [流媒体服务发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/cn/products/adobe-experience-cloud-products.html)的最新发布更新
