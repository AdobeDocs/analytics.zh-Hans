---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d1d08ded701ad68628179874aa6ac21e59ad08dc
workflow-type: tm+mt
source-wordcount: '1440'
ht-degree: 44%

---

# 当前的 Adobe Analytics 发行说明（2026 年 2 月）

**上次更新时间**：2026年2月11日

这些发行说明涵盖2026年2月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **改进的数据馈送** <p>数据馈送现在提供以下改进：</p><ul><li>改善了用户体验。</li><li>提供了创建和管理列模板的新体验。</li><li>您现在可以选择何时创建列模板以供将来数据馈送重复使用。 您还可以删除、编辑和复制模板。<br/>以前，创建的每个数据馈送都会生成一个新的列模板，这会导致大量未使用的列模板，并且无法删除或管理这些模板。</li><li>按标记添加和筛选。</li><li>查看数据馈送作业的历史记录。 （请求时段开始时、开始时、结束时，依此类推。）</li><li>重新发送或重新处理数据馈送。 （从“作业历史记录”页）</li><li>允许迟到的点击。 现在，您可以在设置的报告频率内包含数据馈送作业完成数据处理后到达的数据。</li><li>为数据馈送选择结束日期时，您选择的结束日期将作为数据馈送的最后一天包含在内。<br/>以前，从数据馈送中排除结束日期。</li><li>现在可以提供15分钟导出频率，但默认情况下不可用。 要使此选项在您的环境中可用，您必须首先联系Adobe客户关怀团队，并请求将您的报表包配置为支持15分钟导出。</li></ul><p>**注意：**&#x200B;通过这些改进，Adobe Analytics中的数据馈送页面的URL也在更新中。 请在2026年4月30日之前更新任何现有书签以指向新的数据馈送页面。</p><p>有关详细信息，请参阅[创建数据馈送](/help/export/analytics-data-feed/create-feed.md)和[管理数据馈送](/help/export/analytics-data-feed/df-manage-feeds.md)。</p> | 2026年1月20日 | 2026年2月24日<p>（原计划于2026年2月10日发布）</p> |
| **按多个列对表格进行排序** <p>现在，您可以在 Analysis Workspace 中按多个列（无论是维度还是量度）对自由格式表的数据进行排序。</p><p>当按多个列进行排序时，数据将根据您为每个列指定的优先级进行排序。优先级编号会显示在排序图标旁。</p><p>有关详细信息，请参阅[筛选和排序自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 3 月 <p>（原计划于2026年2月18日）</p> |
| **更新为近似非重复计数函数**<p>Approximate Count Distinct函数中使用的HLL概率算法将很快更新。 使用此函数得出的数字输出可能与历史数字略有不同，如下所示：</p><ul><li>当计算非常少量的唯一值时，将改进结果以使用精确计数，而不是使用估计值。</li><li>在计数任何更大的数字时，计数估计将保持本次更新之前的准确性（估计准确性在准确数字的5%之内，即时间的95%）。</li></ul><p>有关Approximate Count Distinct函数的更多信息，请参阅[高级函数](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct)中的[Approximate Count Distinct](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> |  | 2026 年 3 月 |
| **流媒体服务：支持计划数据** <p>您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪观看人数。</p><p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |
| **新的Adobe Analytics 2.0报表包API指南** <p>创建、检索、更新和删除报表包API。 有关详细信息，请参阅[Adobe Analytics 2.0报表包API参考指南](https://developer.adobe.com/analytics-apis/docs/2.0/apis/report-suites/)和[Adobe Analytics 2.0报表包API端点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/report-suites/)。</p> | | 现在可用 |
| **新的Adobe Analytics 2.0 API异常检测报告指南** <p>创建自动的API异常检测报表。 有关详细信息，请参阅[异常检测API报告终结点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/anomaly/)。</p> | | 现在可用 |
| **新的Adobe Analytics 2.0 API基本日期趋势报告指南** <p>创建自动化API基本日期趋势KPI报告有关详细信息，请参阅[异常检测API报告端点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi/)。</p> | | 现在可用 |

## Adobe Analytics 中的修复

**Activity Map**：
**Analysis Workspace**： AN-424997、AN-424194、AN-425515、AN-423174、AN-425207、AN-428834、AN-306540、AN-426014、AN-427801
**分类**：AN-422723、AN-424467、AN-423724、AN-424003、AN-425217、AN-396062、AN-422744、AN-425456、AN-425271、AN-425655、AN-424894、AN-429236
**数据馈送和Data Warehouse**：AN-427082、AN-405154、AN-406512、AN-423594、AN-425283、AN-425208、AN-422510、AN-421189、AN-428986、AN-426724、AN-401525、AN-426884、AN-425146
**迁移**： AN-421192、AN-423443
**隐私**：
**Report Builder**： AN-391415、AN-425125
**报告**： AN-422123、AN-425817、AN-421097、AN-422249、AN-403446、AN-424727、AN-426791、AN-427985
**计划报告**： AN-425484、AN-425137
**分段**： AN-428905、AN-428232
**Other**： AN-425054、AN-420190、AN-422248


## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **实时流处理改进** | 2026年1月14日 | Adobe计划对LiveStream有效负载的格式进行改进和更改。 这些更新在LiveStream与其他Adobe Analytics功能(如Analysis Workspace)之间提供了更好的对等性。 预览端点可用，可让您测试计划的更改。 有关更改完整列表和预览终结点详细信息，请参阅[LiveStream发行说明](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)。 Adobe计划在2026年4月13日硬性转换到更新的有效载荷格式。 |
| **TLS 1.2密码套件移除** | 2026年2月11日 | 管理员须知： Adobe计划于2026年5月27日从Adobe数据收集服务器中删除对以下TLS 1.2密码包的支持。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>大多数实施不需要客户操作。 此更改主要影响从使用过时TLS库的旧版本机应用程序发送的Analytics数据，以及少量使用过时浏览器或操作系统的Web访客。 取消对这些密码包的支持可增强安全性，并使Adobe与现代加密标准保持一致。 目前，不到0.1%的数据收集流量依赖这些密码套件。</p> |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。新的 Report Builder 仅通过 Microsoft Store 作为插件提供。许多组织要求在向用户提供加载项之前进行内部审批流程。请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **通过旧域或旧 SSO 访问** | 2025年 4 月 10 日 | Adobe 计划更新用户访问 Adobe Analytics 的方式，以增强安全性并简化您的登录体验。作为此项努力的一部分，通过旧域或旧 SSO（包括 `my.omniture.com`）进行的访问将于 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之后，旧版登录凭据和旧版 SSO 将不再起作用。所有用户都必需通过 `experience.adobe.com` 使用他们的 Adobe Experience Cloud ID 登录。如果您需要有关 Experience Cloud ID 方面的帮助，请联系您所在组织的 Adobe Analytics 管理员或 [Adobe 客户服务](https://helpx.adobe.com/cn/contact.html)。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [流媒体服务发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新发布更新
