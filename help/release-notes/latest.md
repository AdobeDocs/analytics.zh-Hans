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
source-git-commit: 01c0296a102b323ea067b2459f79969d507dc744
workflow-type: tm+mt
source-wordcount: 1117
ht-degree: 46%

---

# 当前Adobe Analytics发行说明（2026年9月）

**上次更新日期**：2026年9月9日

这些发行说明涵盖2026年9月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **将区段限制为报表日期范围**<br/>&#x200B;当区段包含日期范围组件时，Workspace报表中的数据可能会超出报表日期范围。<p>现在提供了一个新选项，通过该选项可将结果限制为报表日期范围，而不管该区段中包含的任何日期组件如何。</p><p>创建或修改顶级容器为“访客”的区段时，此选项可用。</p><p>有关详细信息，请参阅[生成区段](/help/components/segmentation/segmentation-workflow/seg-build.md#components)。</p> | 2026年8月26日 | 2026年9月9日 |
| **机器人检测更新**<br/>&#x200B;在将Edge数据收集与Web SDK结合使用时，可以使用以下机器人检测更新：<ul><li>现在，您可以创建机器人检测规则，以识别通信量中的异常，这些异常将被视为机器人生成的异常。 现有和未来的规则将继续默认将匹配流量标记为机器人生成。</li><li>现在，自定义机器人规则先于IAB机器人检测规则运行。 此更改不会影响机器人得分，但与事件关联的机器人规则名称可能会更改。</li></ul><p>注意：此更新仅适用于使用Web SDK的Edge数据收集实施。 它不适用于旧版库，例如AppMeasurement。</p><p>（文档链接将随后提供。）</p> | | 2026年9月初 |
| **分类集API更新**<br/>&#x200B;分类集API文档现在包含用于配置分类集API请求的更新的端点和参数信息。<p>有关详细信息，请参阅[分类终结点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)。</p> | 2026年9月5日 | 2026年9月30日 |
| **2.0 API报告指南中的日期itemId编码指南**<br/> Adobe Analytics 2.0 API日期趋势报告指南现在包含新章节，说明日期`itemId`参数和值的编码方式。 这可以帮助您从现已弃用的1.4 API配置和迁移到2.0 API服务。<p>有关详细信息，请参阅[KPI报告指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi)和[高级报告指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced)。</p> | 2026年9月5日 | 2026年9月30日 |

### Adobe Analytics 中的修复

**Activity Map**： AN-488579、AN-487247、AN-491828
**Analysis Workspace**： AN-487374、AN-487119、AN-468907、AN-468810、AN-468363、AN-468096、AN-467414、AN-466986、AN-466982、AN-465073、AN-463571、AN-462373、AN-492801、AN-488821、AN-488452、AN-486517、AN-478930、AN-468325
**分类**： AN-490825、AN-490802、AN-490549、AN-490472、AN-487782、AN-487286、AN-486531、AN-478859、AN-469929、AN-469033、AN-468944、AN-468827、AN-468592、AN-468326、AN-467115、AN-466995、AN-465636、AN-465616、AN-465380、AN-464911、AN-464338、AN-463677、AN-462729 AN-462577、AN-461040、AN-459316 490072 487100
**数据馈送和Data Warehouse**：AN-487624、AN-487287、AN-479923、AN-479166、AN-479109、AN-468483、AN-493406、AN-492167、AN-333098
**迁移**：
**导出**： AN-467131、AN-469034、AN-447252
**Report Builder**： AN-487486、AN-478944、AN-470036、AN-468589、AN-468436、AN-456747、AN-456700、AN-442695、AN-492330、AN-490564、AN-468293、AN-460921
**报告**： AN-468621、AN-465383、AN-463924
**报表包**： AN-468484、AN-468460、AN-465385、AN-463216
**计划报告**： AN-479157
**分段**： AN-486561， AN-278260
**其他**： AN-488549、AN-467426、AN-465265、AN-464645、AN-459714、AN-459323、AN-454514、AN-487288、AN-470023、AN-469601、AN-320799、AN-316708、AN-309317、AN-266652

### 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能生命周期结束 | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。 所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。 新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。 它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。 为了便于升级，新版 Report Builder 包含一个简便的工作簿转换功能。 新的 Report Builder 仅通过 Microsoft Store 作为插件提供。 许多组织要求在向用户提供加载项之前先完成内部审批流程。 请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | 在&#x200B;**2026年8月31日**，以下Analytics旧版API服务达到其生命周期结束并被关闭，并且任何使用这些服务构建的集成不再起作用：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |

## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。

## 延迟的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的实时内容示例：</p><ul><li>FAST（免费广告支持的电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>有关详细信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)。 | 2025 年 10 月 29 日 | 待定<p>（原计划于2025年10月29日）</p> |


>[!MORELIKETHIS]
>
>* [以前的2026年发行说明](/help/release-notes/2026.md)
>* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
>* [流媒体服务发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新发布更新

