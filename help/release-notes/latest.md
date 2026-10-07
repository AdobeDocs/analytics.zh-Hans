---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: b72328485bde3759519f77c1c3e9509ade6ce2d4
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 53%
---
# 当前Adobe Analytics发行说明（2026年10月）

**上次更新时间**：2026年10月7日

这些发行说明涵盖2026年10月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analytics MCP服务器的只读权限**<br/>&#x200B;管理员现在可以授予用户对Adobe Analytics MCP服务器的只读访问权限。 新的[!UICONTROL MCP只读]权限项允许用户访问所有只读工具，而不允许用户创建项目、区段或计算量度。<p>现有的[!UICONTROL MCP访问]权限项已重命名为[!UICONTROL MCP完全访问]。 具有此权限的用户可保留对所有工具的访问权限，包括创建、更改或删除组件的工具。</p><p>有关详细信息，请参阅[Adobe Analytics MCP服务器](https://developer.adobe.com/analytics-mcp/docs/aa/)。</p> | | 2026年10月6日 |
| **自动生成组件描述** <br/>您现在可以自动生成维度、量度、计算量度、区段和日期范围的描述。 这有助于Workspace用户了解要使用的组件，尤其是在具有大型组件库的组织中。 <p>您可以为单个组件生成描述，或同时为多个组件生成描述。</p> <p>（文档链接见下文。）<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026年10月28日 |
| **Adobe Brand Visibility集成**<br/>&#x200B;将Adobe Brand Visibility与贵组织的Adobe Analytics数据连接起来，以便您可以衡量AI驱动的发现如何转化为真正的网站参与度和业务成果。<p>（文档链接将随后提供。）</p> | | 2026年10 |
| **CX Enterprise Coworker：在同事聊天中分析Adobe Analytics数据** <br/>Adobe CX Enterprise Coworker Chat现在可以执行以前只能在Analysis Workspace中进行的高级数据分析。 同事聊天可访问您的Adobe Analytics报表包中的数据，让您浏览这些数据并获得自然语言提示的答案。<p>（文档链接将随后提供。）</p> | 2026年10月2 | 待定<p>（原计划于2026年9月25日）</p> |

### Adobe Analytics 中的修复

**Activity Map**： AN-494609， AN-493182
**Analysis Workspace**： AN-495340、AN-494789、AN-493307、AN-468900
**分类**： AN-498043、AN-496619、AN-496468、AN-496217、AN-496133、AN-495567、AN-494651、AN-494345、AN-494312、AN-494261、AN-493645、AN-493507、AN-493336、AN-492869、AN-492812、AN-492751、AN-492750、AN-492741、AN-491032、AN-490802、AN-490796、AN-467849
**数据馈送和Data Warehouse**： AN-494937、AN-493065、AN-489796、AN-479109
**迁移**： AN-489850、AN-468014
**导出**： AN-494337， AN-486563
**Report Builder**： AN-496602、AN-494224、AN-493737、AN-493508、AN-493505、AN-492806、AN-468981、AN-454376
**报告**： AN-493637、AN-461260
**报表包**：AN-496773、AN-495227、AN-494981、AN-494372、AN-494370、AN-493629
**计划报告**： AN-491103
**分段**：
**Other**： AN-496398、AN-494453、AN-492494

### 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能生命周期结束 | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版Report Builder加载项已于2026年6月停用。 所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。 新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。 它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。 为了便于升级，新版 Report Builder 包含一个简便的工作簿转换功能。 新的 Report Builder 仅通过 Microsoft Store 作为插件提供。 许多组织要求在向用户提供加载项之前先完成内部审批流程。 请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | 在&#x200B;**2026年8月31日**，以下Analytics旧版API服务达到其生命周期结束并被关闭，并且任何使用这些服务构建的集成不再起作用：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |

## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。

## 延迟的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的实时内容示例：</p><ul><li>FAST（免费广告支持的电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>有关详细信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)。</p> | 2025 年 10 月 29 日 | 待定<p>（原计划于2025年10月29日）</p> |


>[!MORELIKETHIS]
>
>* [以前的2026年发行说明](/help/release-notes/2026.md)
>* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
>* [流媒体服务发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新发布更新

