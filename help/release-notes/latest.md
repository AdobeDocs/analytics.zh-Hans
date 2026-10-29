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
source-git-commit: b3c18ecbee8c2fc80c6743d015ad418f16a6feb4
workflow-type: tm+mt
source-wordcount: '1675'
ht-degree: 29%
---
# 当前Adobe Analytics发行说明（2026年10月）

**上次更新时间**：2026年10月29日

这些发行说明涵盖2026年10月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analytics MCP服务器的只读权限**<br/>&#x200B;管理员现在可以授予用户对Adobe Analytics MCP服务器的只读访问权限。 新的[!UICONTROL MCP只读访问]权限项允许用户访问所有只读工具，而不允许用户创建项目、区段或计算量度。<p>现有的[!UICONTROL MCP访问]权限项已重命名为[!UICONTROL MCP完全访问]。 具有此权限的用户可保留对所有工具的访问权限，包括创建、更改或删除组件的工具。</p><p>有关详细信息，请参阅Adobe Analytics MCP服务器文档中的[设置权限](https://developer.adobe.com/analytics-mcp/docs/guides/permissions)。</p> | | 2026年10月6日 |
| **历程画布：比较百分比**<br/>&#x200B;将历程与前期进行比较时，现在可启用新的[!UICONTROL 比较百分比]选项，以显示每个节点、箭头和流失的百分比变化。 在比较比率（例如节点之间的维系率或流失率）时，这项功能非常有用，因为即使旅程中的人数在日期范围之间不同，比较仍会保持准确。<p>有关详细信息，请参阅[配置历程画布可视化图表](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#configure-visualization-settings)中的“比较百分比”。</p> | | 2026年10月19 |
| **可视化中的简洁图例标签**<br/>&#x200B;您现在可以缩短可视化图例标签，以便一目了然地区分它们。 [!UICONTROL 简洁标签]设置通过删除每个标签共享的量度、区段、维度项或日期范围名称，智能地关注区分不同标签的信息。<p>如果没有简洁的标签，则每个图例标签都会重复共享名称，这可能会导致标签变长，其差异仅在悬停时可见。</p><p>默认情况下，简洁的标签处于关闭状态，并且可用于区域、条形图、组合图、圆环图、直方图、水平条形图、折线图和维恩图（包括栈叠版本）可视化图表。</p><p>有关详细信息，请参阅[简洁的标签](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concise-labels)。</p> | | 2026年10月29日 |
| **自动为组件和项目生成描述** <br/>您现在可以自动生成维度、量度、计算量度、区段和日期范围的描述。 这有助于Workspace用户了解要使用的组件，尤其是在具有大型组件库的组织中。 <p>您可以为单个组件生成描述，或同时为多个组件生成描述。 有关详细信息，请参阅[自动生成描述](/help/analyze/analysis-workspace/components/add-component-descriptions.md#automatically-generate-descriptions)。</p><p>在[保存项目](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)或从[项目信息和设置](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)中为Workspace项目生成描述。</p> | 2026年10月29日 | 2026年11月11 |
| **Data Warehouse报表中的分类数据改进**<br/> Data Warehouse报表中的分类数据现在更准确。 通过这些改进，您可能会注意到Data Warehouse报表中的以下差异：<ul><li>**您以前看到分类值的空白值**：从分类集中删除分类值时，Data Warehouse现在可以正确显示空白。 以前，已删除的分类值可能会继续显示在以后的报表中。</li><li>**更完整的分类值**：在某些情况下，Data Warehouse以前只显示几个不同分类值中的一个。 Data Warehouse现在显示每个值。</li><li>**在Analysis Workspace中，分类值的表示方式可能有所不同（不常见）**： Data Warehouse可以显示所有关联的分类值，而Analysis Workspace只显示一个值。 因此，Data Warehouse和Analysis Workspace之间的分类值有时可能会有所不同。</li></ul><p>有关详细信息，请参阅Data Warehouse中的[分类维度](/help/export/data-warehouse/component-support.md#classifications)。</p> | 2026年10月14 | 2027年1月 |
| **Adobe Brand Visibility集成**<br/>&#x200B;将Adobe Brand Visibility与贵组织的Adobe Analytics数据连接起来，以便您可以衡量AI驱动的发现如何转化为真正的网站参与度和业务成果。<p>（文档链接将随后提供。）</p> | | 待定<br/>（原计划于2026年10月发布） |
| **CX Enterprise Coworker：在同事聊天中分析Adobe Analytics数据** <br/>Adobe CX Enterprise Coworker Chat现在可以执行以前只能在Analysis Workspace中进行的高级数据分析。 同事聊天可访问您的Adobe Analytics报表包中的数据，让您浏览这些数据并获得自然语言提示的答案。<p>有关详细信息，请参阅Adobe CX Enterprise Coworker文档中的[使用同事聊天分析数据](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-overview)。</p> | 2026年10月2 | 2026年10月29日<p>（原计划于2026年9月25日）</p> |
| **CX Enterprise Coworker： Adobe Analytics数据的根本原因分析**<br/>&#x200B;同事聊天现在可以调查为什么某个指标在您的Adobe Analytics报表包中发生了更改，而不是只报告该指标发生了更改。 询问已知量度在已知时间段内的变化（例如“为什么周二收入激增？”），同事聊天会揭示出促成该变化的维度和区段。<p>有关详细信息，请参阅Adobe CX Enterprise Coworker文档中的[业务绩效概述](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/business-performance/business-performance)。</p> | 2026年10月13 | 2026年10月29日 |
| **CX Enterprise Coworker：在Analysis Workspace中打开可视化图表**<br/>&#x200B;当同事聊天根据您的Adobe Analytics数据创建可视化图表时，您现在可以在新的Analysis Workspace项目中打开该可视化图表，以便进行更深入的分析并更精细地控制。 <p>有关详细信息，请参阅Adobe CX Enterprise Coworker文档中的[在Analysis Workspace中打开可视化图表](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat#open-a-visualization-in-analysis-workspace)。</p> | 2026年10月13 | 2026年10月29日 |
| **CX Enterprise Coworker：将项目迁移到Customer Journey Analytics**<br/>&#x200B;您现在可以使用同事将Adobe Analytics项目及其相关组件迁移到Customer Journey Analytics。 同事会验证项目中的维度和量度是否已映射到Customer Journey Analytics数据视图，帮助您映射任何未映射的维度和量度，然后在Customer Journey Analytics中重新创建项目。 具有[!UICONTROL 组件迁移]权限的用户可以使用同事迁移项目，即使他们不是管理员。 <p>以前，您只能在Adobe Analytics用户界面中或通过Adobe Analytics 2.0 API迁移项目。</p><p>有关详细信息，请参阅Adobe Analytics文档中的[与同事一起将Adobe CX Enterprise Coworker项目迁移到Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/intelligent-implementation-and-administration/migrate-projects-aa-cja)。</p> | | 2026年10月29日 |

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

