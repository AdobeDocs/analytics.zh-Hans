---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 07d6b4e096d239d4940f438c5eca46f496a18131
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 42%

---

# 当前Adobe Analytics发行说明（2025年8月版）

**上次更新日期**：2025年8月13日

这些发行说明涵盖2025年8月13日至9月16日的发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **使用新的反向链接类型维度项分析AI流量** | 10月，将提供新的反向链接类型维度项目，以帮助分析来自AI工具的流量。 <p>这个新的反向链接类型维度项目称为对话式人工智能工具，它将主要人工智能工具的反向链接域分组在一起，以便您查看整个组的趋势。 此新类别中反向链接域的初始列表包括（但不限于）：</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>新的维度项目将在所有与Adobe Analytics相关的工具中可用，包括Analysis Workspace、Report Builder、Data Warehouse、数据馈送等。</p><p>使用此新维度项时，请考虑以下事项：</p><ul><li>并非总是能够区分来自搜索引擎“AI模式”中提供的结果的反向链接流量与来自点进次数与传统的搜索结果的反向链接流量。</li><li>新的对话人工智能工具维度项目重点关注流量最多的主要提供商。 新趋势显示，越来越多的模拟者网站使用与主要AI工具提供商类似的域。 这可能是由于个人或团体可以轻松地创建自己的人工智能工具并将其托管在互联网上。 由于这是一个快速演变的空间，如果您发现不包括某个热门网站，请联系Adobe支持团队。</li><li>反向链接类型维度（包括新的对话人工智能工具维度项）仅可用于Adobe Analytics处理的数据。 </li></ul><p>（文档链接见下文。）</p> |   | 10 月 2025 日 |
| **以 PDF 格式下载的项目将保存到您的工作站** | 将项目下载为PDF时，PDF将下载到您工作站上的下载文件夹中。 <p>以前，将项目下载为PDF会在新的浏览器选项卡中启动一个具有唯一URL的PDF。</p><p>有关详细信息，请参阅[下载项目和数据](/help/analyze/analysis-workspace/curate-share/download-send.md)</p> |  | 2025 年 8 月 25 日 |
| **删除的项目将通过URL立即不可用，并且将从计划的投放中删除** | 已删除的项目会立即从计划投放中删除，并且不再可通过其URL访问。<p>以前，项目包含在计划交付中，可在删除项目后60天内通过其URL进行访问。</p><p>有关删除项目的详细信息，请参阅[项目概述](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)。</p> | | 2025年8月底 |
| **流媒体：更新了用于将流媒体数据收集到Adobe Experience Platform的XDM字段** | 将流媒体数据收集到 Adobe Experience Platform 时，不再使用流媒体参数文档中“XDM 字段路径”标题下显示的 XDM 字段路径。相反，如果在2025年5月9日之前实施了Analytics Source Connector以将流媒体数据收集到Platform，则客户必须将其现有配置迁移到mediaReporting字段路径，如流媒体参数文档的“报告XDM字段路径”标题下所示。<p> 这些字段路径可在以下页面上找到并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/quality-parameters)。 （对于在2025年5月9日后实施Analytics源连接器并且已经在仅使用mediaReporting XDM路径的客户，无需执行任何操作。）</p><p>已弃用的XDM字段路径上的数据摄取将持续到2025年10月底。 之后，已弃用的字段路径将完全删除，并且在Adobe Experience Platform架构UI中将不再可见，数据将仅使用mediaReporting字段路径发送。</p><p>有关详细信息，请参阅[将Analytics Source Connector实施迁移到更新的XDM流媒体字段](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>有关迁移支持，请联系您的Adobe Consulting服务或帐户团队。 </p> |  | 10 月 2025 日 |

## Adobe Analytics 中的修复

**Activity Map**： AN-389205； AN-384186
**Analysis Workspace**： AN-390102、AN-389066、AN-388841、AN-388687、AN-388478、AN-387089、AN-387044、AN-384560、AN-379213、AN-351639
**分类**： AN-390442、AN-390385、AN-389953、AN-389703、AN-389321、AN-389116、AN-388833、AN-388717、AN-387987、AN-383329
**数据收集**： AN-389320
**数据馈送和Data Warehouse**： AN-389702； AN-388136； AN-387779； AN-384369； AN-383075； AN-380307
**隐私**：
**Report Builder**： AN-389336； AN-382775
**报告**： AN-390398
**计划报告**：
**区段比较**：
**Other**： AN-388180； AN-383164； AN-366532


## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。所有用户都应开始将其旧工作簿升级到[新的 Report Builder](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/rb-overview)。新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。它具有[几乎相同的功能](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/convert-workbooks#unsupported)以及许多新的便捷功能和 UI 增强功能。要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。新的 Report Builder 仅通过 Microsoft Store 作为插件提供。许多组织要求在向用户提供加载项之前进行内部审批流程。请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **通过旧域或旧 SSO 访问** | 2025年 4 月 10 日 | Adobe 计划更新用户访问 Adobe Analytics 的方式，以增强安全性并简化您的登录体验。作为此项努力的一部分，通过旧域或旧 SSO（包括 `my.omniture.com`）进行的访问将于 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之后，旧版登录凭据和旧版 SSO 将不再起作用。所有用户都必需通过 `experience.adobe.com` 使用他们的 Adobe Experience Cloud ID 登录。如果您需要有关 Experience Cloud ID 方面的帮助，请联系您所在组织的 Adobe Analytics 管理员或 [Adobe 客户服务](https://helpx.adobe.com/cn/contact.html)。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
