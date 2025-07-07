---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 91a17aa9ae7a0a6c6b7a1fd8d5ffe5d7d2efb294
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 94%

---

# 当前的 Adobe Analytics 发行说明（2025 年 6 月版本）

**上次更新时间**：2025年7月7日

这些发行说明涵盖 2025 年 6 月 18 日至 7 月 15 日的发行期。Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **使用算法的Livestream TNT字段** | 直播串流正在进行更新，以确保技术继续保持现代和稳定。 作为此刷新的一部分，如果您的TNT字段中有一个算法，我们将开始将TNT字段合并到Livestream输出中。 但是，这仅包括以前支持的元素： `campaignId`、`recipeId`、`trafficType`、`actionId`和`actionName`。 Livestream的整个TNT架构保持不变。 |   | 7,2025 年 7 月 |
| **新版本 Report Builder 支持安全的云目标** | JavaScript Report Builder 插件现已支持将报表导出至以下云存储目标：<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>以前，只有 FTP 和电子邮件目标可用。由于安全问题，FTP 不再受支持。</p><p>有关详细信息，请参阅[通过导出到云目标来安排工作簿](/help/analyze/report-builder/report-builder-export.md)。</p><p>除了这些更新外，在 Adobe Analytics 中创建位置时，“使用方式”字段现在新增了将该位置与 Report Builder 搭配使用的选项，相关说明详见[配置云导入与导出位置](/help/components/locations/configure-import-locations.md)。</p> |  | 2025 年 6 月 19 日（原定 6 月 18 日） |
| **新预览体验** | 在创建区段或配置数据视图设置时使用的预览面板，现在已将原先的圆环图可视化图表更改为水平条形图可视化图表。 |  | 2025 年 6 月 18 日 |
| **修改了归因模型对话框** | 您现在可以在归因模型对话框中分别定义容器和时段。 |  | 2025 年 6 月 18 日 |
| **更新了客户属性 UI 的导航** | 现在可以直接从 Adobe Experience Cloud 中的应用程序选择器访问客户属性用户界面。 |  | 待定 |
| **流媒体：支持计划数据** | 您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪观看人数。以下是支持计划数据上传的直播内容示例：<ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。无论您如何实现流媒体收集，这些功能都是可用的。<p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。了解详情 |  | 2025 年 8 月 15 日（原定为 2025 年 6 月 25 日） |

## Adobe Analytics 中的修复

**A4T**: AN-379045
**Advertising Analytics**: AN-377338
**警报**: AN-377229
**Analysis Workspace**: AN-378891; AN-379589; AN-379604; AN-381270; AN-382264; AN-382414；
**API 1.4**: AN-380188
**API 2.0**: AN-373078；AN-379006；AN-381248
**分类**：AN-379209；AN-379315；AN-379567；AN-379573；AN-379749；AN-379764；AN-379818；AN-380433；AN-381670；AN-381751；AN-381994；AN-382055；AN-382682；AN-383059；AN-383409
**贡献度分析**：AN-369822
**数据馈送**：AN-365552；AN-367158；AN-378288；AN-379754；AN-380433；AN-380855；AN-380959；AN-381115；AN-381657；AN-381931
**Data Warehouse**：AN-379244
**平台**：AN-375847
**处理规则**：AN-375157
**Report Builder**：AN-371395；AN-372174；AN-373815；AN-383194
**服务器调用**：AN-380930
**使用和访问日志**：AN-372130；AN-382123
**虚拟报告包**：AN-382010


## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。所有用户都应开始将其旧工作簿升级到[新的 Report Builder](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/rb-overview)。新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。它具有[几乎相同的功能](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/convert-workbooks#unsupported)以及许多新的便捷功能和 UI 增强功能。要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。新的 Report Builder 仅通过 Microsoft Store 作为插件提供。许多组织要求在向用户提供加载项之前进行内部审批流程。请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **通过旧域或旧 SSO 访问** | 2025年 4 月 10 日 | Adobe 计划更新用户访问 Adobe Analytics 的方式，以增强安全性并简化您的登录体验。作为此项努力的一部分，通过旧域或旧 SSO（包括 `my.omniture.com`）进行的访问将于 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之后，旧版登录凭据和旧版 SSO 将不再起作用。所有用户都必需通过 `experience.adobe.com` 使用他们的 Adobe Experience Cloud ID 登录。如果您需要有关 Experience Cloud ID 方面的帮助，请联系您所在组织的 Adobe Analytics 管理员或 [Adobe 客户服务](https://helpx.adobe.com/cn/contact.html)。 |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 6 月 30 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |



## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
