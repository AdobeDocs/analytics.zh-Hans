---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d16214865a037efe41b9f95682758daa577a12ed
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 87%

---

# 当前Adobe Analytics发行说明（2025年10月版）

**上次更新日期**：2025 年 10 月 14 日

这些发行说明涵盖 2025 年 10 月至 11 月初的发行期。Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **包含在线形图可视化图表和迷你图中的筛选条件** | 现在，应用于自由格式表过滤器的任何搜索筛选条件始终包含在迷你图中。此外，您还可以在任何连接的线形图可视化图表中包含搜索筛选条件。<p>您可以通过选择所连接表的量度列标题中的迷你图，将线形图可视化图表配置为包含搜索筛选条件。</p><p>以前，搜索筛选条件未包含在迷你图或连接的线形图可视化图表中。</p><p>有关详细信息，请参阅[查看自由格式表的趋势数据](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md)。</p> | | 2025 年 10 月 15 日 |
| **通过新的“反向链接类型”维度项分析 AI 流量** | 我们将推出一个新的反向链接类型维度项，帮助分析来自 AI 工具的流量。 <p>这个新的反向链接类型维度项称为“对话式 AI 工具”，它将主要 AI 工具的反向链接域合成一组，让您可以查看该组作为整体的趋势。这个新类别中的反向链接域初始列表包括（但不限于）：</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>这个新的维度项将在所有 Adobe Analytics 相关的工具中提供，包括 Analysis Workspace、Report Builder、数据仓库、数据馈送等。</p><p>使用新的维度项时请考虑以下事项：</p><ul><li>并不总是能够区分来自搜索引擎中“AI 模式”所提供结果的引荐流量与来自传统搜索结果点进而产生的引荐流量。</li><li>新的对话式 AI 工具维度项重点关注带来最多流量的主要提供商。新的趋势表明，越来越多的模仿网站具有与主要 AI 工具提供商相似的域。这可能是因为个人或团体可以非常轻松地创建自己的 AI 工具并将其托管在互联网上。由于这是一个快速发展的领域，如果您发现某个热门网站未包含在内，请联系 Adobe 支持团队。</li><li>反向链接类型维度，包括新的对话式 AI 工具维度项，仅适用于 Adobe Analytics 处理的数据。 </li></ul><p>有关此新维度项的更多信息，请参阅[反向链接类型](/help/components/dimensions/referrer-type.md)维度，该维度包括[对话AI工具维度项](/help/components/dimensions/referrer-type.md#conversational-ai-tools)。 此维度项包括预定义的AI聊天机器人列表。</p><p>有关使用Adobe Analytics分析AI流量的一般信息，请参阅[分析来自对话AI工具的流量](/help/technotes/ai-traffic.md)。</p> |   | 2025 年 10 月 15 日 |
| **流媒体服务：支持计划数据** | 您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>（文档链接见下文。）<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025 年 10 月 29 日 |
| **流媒体服务：更新了用于将流媒体数据收集到 Adobe Experience Platform 的 XDM 字段** | 将流媒体数据收集到 Adobe Experience Platform 时，不应再使用流媒体参数文档中“XDM 字段路径”标题下显示的 XDM 字段路径。在 2025 年 5 月 9 日之前实施了 Analytics 源连接器以将流媒体数据收集到平台的客户，必须将其现有配置迁移到 mediaReporting 字段路径，参见流媒体参数文档中“报告 XDM 字段路径”标题下的段落。<p> 这些字段路径位于以下页面并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/quality-parameters)。（2025 年 5 月 9 日之后实施 Analytics 源连接器，并且只使用 mediaReporting XDM 路径的客户无需采取任何行动。）</p><p>在已弃用的 XDM 字段路径上的数据摄取将继续进行，直到 2025 年 10 月底。之后，已弃用的字段路径将被完全移除，并且不再显示在 Adobe Experience Platform Schema UI 中，届时起将只使用 mediaReporting 字段路径发送数据。</p><p>有关详细信息请参阅[将 Analytics 源连接器实施迁移到更新后的 XDM 流媒体字段](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>请联系您的 Adobe Consulting 服务或帐户团队以获取迁移支持。 </p> |  | 2025 年 10 月 |
| **Adobe Analytics 2.0 API报告包创建** | 在Adobe Analytics中使用2.0 API创建报表包。 新的POST方法取代了1.4报表包API的创建，为即将弃用1.4 API做准备。 | | 2025年10月25日 |

## Adobe Analytics 中的修复

**Activity Map**：
**Analysis Workspace**： AN-399209、AN-397146、AN-394992、AN-390795
**分类**：AN-400583、AN-399205、AN-398580、AN-398257、AN-395921、AN-394973
**数据收集**：
**数据馈送和Data Warehouse**：AN-400938、AN-399075、AN-398924、AN-398573、AN-396574、AN-393946
**隐私**：
**Report Builder**： AN-401127、AN-400618、AN-392971、AN-391692
**报告**：
**计划报告**：
**区段比较**：
**Other**： AN-396084


## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。新的 Report Builder 仅通过 Microsoft Store 作为插件提供。许多组织要求在向用户提供加载项之前进行内部审批流程。请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **通过旧域或旧 SSO 访问** | 2025年 4 月 10 日 | Adobe 计划更新用户访问 Adobe Analytics 的方式，以增强安全性并简化您的登录体验。作为此项努力的一部分，通过旧域或旧 SSO（包括 `my.omniture.com`）进行的访问将于 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之后，旧版登录凭据和旧版 SSO 将不再起作用。所有用户都必需通过 `experience.adobe.com` 使用他们的 Adobe Experience Cloud ID 登录。如果您需要有关 Experience Cloud ID 方面的帮助，请联系您所在组织的 Adobe Analytics 管理员或 [Adobe 客户服务](https://helpx.adobe.com/cn/contact.html)。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [流媒体服务发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新发布更新
