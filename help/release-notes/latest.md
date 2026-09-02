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
source-git-commit: 2258ee4b539ec7ce7366c427fede2c5b8483db7f
workflow-type: tm+mt
source-wordcount: 1246
ht-degree: 43%

---

# 当前Adobe Analytics发行说明（2026年8月）

**上次更新日期**：2026年8月5日

这些发行说明涵盖2026年8月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **Activity Map扩展： UI刷新** <br/>Activity Map Overlay扩展具有更新的外观，以及支持即将推出的增强功能的基础改进。<p>有关Activity Map叠加扩展的信息，请参阅[Activity Map扩展接口](/help/analyze/activity-map/overlay/overview.md)。</p> | | 2026年8月5日<p>（原计划于7月底发布）</p> |
| **历程画布增强功能**<br>&#x200B;现已提供以下历程画布增强功能：<ul><li>将历程与先前的时间范围进行比较。 将当前历程与4周前、2个季度前、1年前或自定义日期范围前的历程进行比较。</li><li>对于所选节点，显示历程中任意时间点上所选节点之后排名最前的维度项目。 当所选节点是分析中的关键事件，并且您想要查看用户随后在任何时候执行的操作时，可使用此选项。<p>以前，只有顶级的直接节点才能显示在选定节点之前或之后。 </p></li><li>更改节点之间箭头的形状和样式。 在节点之间拖动箭头可更改箭头的形状（曲率），右键单击箭头可将其样式更改为下列任一类型：实线、虚线、点线、虚线点或动画。</li></ul><p></p>有关详细信息，请参阅[配置历程画布可视化图表](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。 | | 2026年8月18日 |
| **将区段限制为报表日期范围**<br/>&#x200B;当区段包含日期范围组件时，Workspace报表中的数据可能会超出报表日期范围。<p>现在提供了一个新选项，通过该选项可将结果限制为报表日期范围，而不管该区段中包含的任何日期组件如何。 <p>创建或修改顶级容器为“访客”的区段时，此选项可用。</p><p>有关详细信息，请参阅[生成区段](/help/components/segmentation/segmentation-workflow/seg-build.md#components)。</p> | 2026年8月26日 | 2026年9月9日 |
| **Analytics API营销渠道参考**<br/>&#x200B;使用Adobe Analytics 2.0 API营销渠道参考检索Analytics营销渠道信息。 请参阅[Analytics API营销渠道参考](https://developer.adobe.com/analytics-apis/docs/2.0/apis/marketing-channels)。 | | 2026年8月1日 |
| **Analytics API营销渠道端点指南**<br/> Adobe Analytics 2.0 API营销渠道端点指南提供了使用该端点的说明和示例。 请参阅[Analytics API营销渠道端点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/marketing-channels)。 | | 2026年8月1日 |
| **Analytics 1.4 API EOL客户常见问题解答**<br/> Analytics 1.4 API EOL客户常见问题解答提供了有关最近2.0 API开发的信息，以帮助客户离开1.4 API。 | | 2026年8月10日 |

### Adobe Analytics 中的修复

**Activity Map**： AN-404862
**Analysis Workspace**： AN-466867、AN-465995、AN-465315、AN-465313、AN-464375、AN-463634、AN-463248、AN-463175、AN-463049、AN-462347、AN-462124、AN-461922、AN-458398、AN-457849、AN-455002、AN-453357、AN-456863、AN-459816、AN-459034、AN-460774、AN-460671、AN-457760、AN-443594
**分类**： AN-467138、AN-467118、AN-467069、AN-466054、AN-465987、AN-465636、AN-465380、AN-464650、AN-464286、AN-463688、AN-462413、AN-462252、AN-462141、AN-462063、AN-462005、AN-461862、AN-461806、AN-461777、AN-461158、AN-460954、AN-460905、AN-460850、AN-460803 AN-460272、AN-460023、AN-459814、AN-459367、AN-459328、AN-459300、AN-459279、AN-459006、AN-458417、AN-458403、AN-457829、AN-457400、AN-454408、AN-449670、AN-460956、AN-459269、AN-458789、AN-461778、AN-461191、AN-460996、AN-460506、AN-459988、AN-459854、AN-458994、AN-457561 AN-457055， AN-454224， AN-454172， AN-459473 459277 459026 455270
**数据馈送和Data Warehouse**：AN-465273、AN-464245、AN-462435、AN-461000、AN-460700、AN-459225、AN-459192
**迁移**： AN-458185、AN-454285、AN-459239
**导出**：
**Report Builder**： AN-465346、AN-464768、AN-464580、AN-464301、AN-463048、AN-462800、AN-457042、AN-461033、AN-459042、AN-454250、AN-451735、AN-450776、AN-450200、AN-451665
**报告**： AN-467107、AN-459010、AN-455619、AN-459530、AN-454103
**报表包**： AN-464246、AN-463756、AN-462101
**计划报告**： AN-455009、AN-460037、AN-462093
**分段**： AN-459002、AN-457730、AN-457146
**Other**： AN-467386、AN-466935、AN-462116、AN-458836、AN-451292、AN-454160、AN-458354、AN-455771、AN-426869、AN-437975

### 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能生命周期结束 | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。 所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。 新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。 它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。 为了便于升级，新版 Report Builder 包含一个简便的工作簿转换功能。 新的 Report Builder 仅通过 Microsoft Store 作为插件提供。 许多组织要求在向用户提供加载项之前先完成内部审批流程。 请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |

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

