---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2: id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 0d5c4866332fcbc8195e59babd01abc95444ffac
workflow-type: tm+mt
source-wordcount: 959
ht-degree: 59%

---

# 当前Adobe Analytics发行说明（2026年7月）

**上次更新日期**：2026年7月8日

这些发行说明涵盖2026年7月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **子点击分析** <br/>子点击分析允许您在比点击级别更精细的级别分析产品数据。 您可以对点击中的单个产品进行分段，而不是对整个点击进行过滤。 <p>例如，您可以按特定产品类别进行分段，而不包括同一订单中购买的所有其他产品。</p><p>有关详细信息，请参阅[子点击分析](/help/components/segmentation/sub-hit.md)。</p> | 7月8日 | 2026年7月底 |
| **Activity Map扩展： Web SDK支持和UI刷新** <br/>Adobe Analytics的Web SDK实施现在可以使用Activity Map覆盖扩展查看其网站上覆盖的点击数据。<p>以前，Activity Map Overlay扩展仅可用于AppMeasurement实施。</p> <p>除了Web SDK支持之外，Activity Map Overlay扩展还包括更新的外观。</p><p>（文档链接见下文。）</p> | | 2026年7月底 |
| **AA 2.0 API搜索功能指南** <br/>使用搜索功能[返回报告中的维度项子集](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters)。<p>有关详细信息，请参阅Adobe Developer上的报表端点指南中的[搜索功能](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters)。 | | 2026年7月1日 |
| **使用AA API自动定期报告** <br/>使用报表API按计划新鲜指标为数据管道设置自动的定期Adobe Analytics报告。 <p>有关详细信息，请参阅Adobe Developer上的[自动循环Analytics报表端点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/recurring)。</p> | | 2026年7月1日 |
| **AA的新扩展参数** <br/>使用新的Dimension API扩展参数检索分配类型、过期时间、数据类型和促销的eVar配置字段。 <p>有关详细信息，请参阅Adobe Developer上的[API引用](https://developer.adobe.com/analytics-apis/docs/2.0/apis/#operation/dimensions_getDimensions)和[维度端点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)。</p> | | 2026年7月1日 |

### Adobe Analytics 中的修复

**Activity Map**：
**Analysis Workspace**： AN-449890、AN-457527、AN-451161、AN-459034、AN-458071、AN-458398
**分类**：AN-453318、AN-456739、AN-455828、AN-455270、AN-460272、AN-459367、AN-459239、AN-458418、AN-458417
**数据馈送和Data Warehouse**： AN-456945、AN-460700
**迁移**：
**导出**：
**Report Builder**： AN-457533， AN-453683
**报告**： AN-447692、AN-451259、AN-455713
**报告包**：
**计划报告**： AN-450715
**分段**：
**Other**： AN-453982、AN-455771

### 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。 所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。 新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。 它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。 要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。 新的 Report Builder 仅通过 Microsoft Store 作为插件提供。 许多组织要求在向用户提供加载项之前进行内部审批流程。 请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |

## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。

## 延迟的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data) | 2025 年 10 月 29 日 | 待定<p>（原计划于2025年10月29日）</p> |


>[!MORELIKETHIS]
>
>* [以前的2026年发行说明](/help/release-notes/2026.md)
>* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
>* [流媒体服务发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新发布更新

