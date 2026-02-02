---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1ef9c5fc39174f9b0313fc8b738ed0da35273c18
workflow-type: tm+mt
source-wordcount: '1231'
ht-degree: 53%

---

# 当前 Adobe Analytics 发行说明（2026 年 1 月）

**上次更新日期**：2026 年 1 月 14 日

本发行说明涵盖 2026 年 1 月的发布周期。Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **分类集规则生成器** | [规则生成器](/help/components/classifications/sets/manage/rules.md)功能现在可用于分类集中。 您可以在分类集的上下文中定义规则。 规则将应用（激活时）到订阅了分类集的所有报表包和键维度组合。</p> |  | 2026年1月23日 |
| **改进的数据馈送** | 数据馈送有以下改进功能：<ul><li>改善了用户体验。</li><li>提供了创建和管理列模板的新体验。</li><li>您现在可以选择何时创建列模板以供将来数据馈送重复使用。 您还可以删除、编辑和复制模板。<br/>以前，创建的每个数据馈送都会生成一个新的列模板，这会导致大量未使用的列模板，并且无法删除或管理这些模板。</li><li>按标记添加和筛选。</li><li>查看数据馈送作业的历史记录。 （请求时段开始时、开始时、结束时，依此类推。）</li><li>重新发送或重新处理数据馈送。 （从“作业历史记录”页）</li><li>允许迟到的点击。 现在，您可以在设置的报告频率内包含数据馈送作业完成数据处理后到达的数据。</li><li>为数据馈送选择结束日期时，您选择的结束日期将作为数据馈送的最后一天包含在内。<br/>以前，从数据馈送中排除结束日期。</li><li>现在可以提供15分钟导出频率，但默认情况下不可用。 要使此选项在您的环境中可用，您必须首先联系Adobe客户关怀团队，并请求将您的报表包配置为支持15分钟导出。</li></ul><p>**注意：**&#x200B;通过这些改进，Adobe Analytics中的数据馈送页面的URL也在更新中。 请在2026年4月30日之前更新任何现有书签以指向新的数据馈送页面。</p>（文档链接见下文。）</p> | 2026年1月20日 | 2026年2月24日 <p>（原计划于2026年2月10日发布）</p> |
| **按多个列对表格进行排序** | 现在，您可以在 Analysis Workspace 中按多个列（无论是维度还是量度）对自由格式表的数据进行排序。<p>当按多个列进行排序时，数据将根据您为每个列指定的优先级进行排序。优先级编号会显示在排序图标旁。</p><p>有关详细信息，请参阅[筛选和排序自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **流媒体服务：支持计划数据** | 您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |

## Adobe Analytics 中的修复

**Activity Map**：
**Analysis Workspace**： AN-423389、AN-422636、AN-422482、AN-422027、AN-421134、AN-420187、AN-406271、AN-406188、AN-405997、AN-405983、AN-405796、AN-405033、AN-404893、AN-404871、AN-404842、AN-404713、AN-404502、AN-404353、AN-404352、AN-404048、AN-402523、AN-396149、AN-390990 an-390728、AN-390646、AN-383484、AN-376980 371729 347570
**分类**：AN-423985、AN-423092、AN-423067、AN-422913、AN-422908、AN-422793、AN-422785、AN-422745、AN-422705、AN-422422、AN-422126、AN-422098、AN-422077、AN-422058、AN-421999、AN-421698、AN-421351、AN-406583、AN-406295、AN-406123、AN-406052、AN-404743、AN-404372
**数据收集**： AN-422488
**数据馈送和Data Warehouse**：AN-423186、AN-422789、AN-422239、AN-421552、AN-421393、AN-421339、AN-421231、AN-420149、AN-406345、AN-406217、AN-405073、AN-404822、AN-404774、AN-389691
**隐私**：
**Report Builder**： AN-422120、AN-421937、AN-406296、AN-402951、AN-399748
**报告**：
**计划报告**： AN-423087、AN-422686
**区段比较**：
**Other**： AN-423401、AN-422819、AN-422775、AN-422626、AN-422238、AN-422160、AN-422071、AN-421687、AN-420045、AN-404891、AN-404608、AN-390912


## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **实时流处理改进** | 2026年1月14日 | Adobe计划对LiveStream有效负载的格式进行改进和更改。 这些更新在LiveStream与其他Adobe Analytics功能(如Analysis Workspace)之间提供了更好的对等性。 预览端点可用，可让您测试计划的更改。 有关更改完整列表和预览终结点详细信息，请参阅[LiveStream发行说明]。 Adobe计划在2026年4月13日硬性转换到更新的有效载荷格式。 |
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
