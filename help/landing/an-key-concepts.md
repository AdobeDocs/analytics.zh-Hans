---
description: 此部分包含 Adobe Analytics 的关键概念、有关这些概念的简要描述，以及提供有关该主题的更多详细信息的特定文档链接。
title: Adobe Analytics - 关键概念
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '1858'
ht-degree: 100%

---


# Adobe Analytics - 关键概念

此部分包含 Adobe Analytics 的关键概念、有关这些概念的简要描述，以及提供有关该主题的更多详细信息的特定文档链接。

## Analytics 工具 {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 产品 | 描述 | 文档链接 |
| --- | --- | --- |
| Analysis Workspace | 用于构建强大的自定义分析项目和实现分析民主化的浏览器解决方案。具有比 Reports and Analytics 更大的报告灵活性 | [Analysis Workspace 主页](/help/analyze/analysis-workspace/home.md) |
| Reports and Analytics（以前称为 SiteCatalyst） | 用于报告和分析的浏览器解决方案。Analytics 包中的初学者工具。 | [Reports and Analytics 主页](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | 允许您通过 Adobe Analytics 数据构建自定义请求并使用 Microsoft Excel 实现可视化的 Excel 外接程序。 | [Report Builder 主页](/help/analyze/report-builder/home.md) |
| Data Workbench（以前称为 Insight） | 旨在收集、处理、分析与可视化来自多个渠道间在线和离线客户交互的数据。 | [Data Workbench 客户端](https://docs.adobe.com/content/help/zh-Hans/data-workbench/using/client/t-open-ins.html) |
| Data Warehouse | 用于存储和自定义报表的、未经处理的原始数据，您可通过过滤数据运行它。无点击级别。 | [Data Warehouse 主页](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | 可以在整个 Adobe Experience Cloud 范围内将移动设备应用程序的移动营销功能整合在一起，以便您了解和提高应用程序的用户参与度。 | [Mobile Services 主页](https://docs.adobe.com/content/help/zh-Hans/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors（以前称为 Genesis） | 可将来自第三方应用程序的跟踪数据导入 Analytics，从而在一个中心位置提供端到端的性能可见性。Adobe 决定自 2021 年 8 月 1 日起，中断 Data Connector 集成。 | [Data Connectors 主页](/help/import/data-connectors/data-connectors-eol.md) |
| Dynamic Tag Management (DTM) | 帮助您管理所有网站上的 Analytics、Target 及其他标签，而无需考虑您有多少个域。 | [DTM 主页](/help/implement/other/dtm/dtm-implementation-overview.md) |
| Adobe Launch | Adobe 推出的新一代网站标记和移动 SDK 管理功能。 | [Adobe Launch 主页](https://docs.adobe.com/content/help/zh-Hans/launch/using/overview.translate.html) |

## 关键术语 {#concept_E473ACBB8E4A42B4AC005538AC12F154}

单击[此处](/help/technotes/terms.md)，以获取有关 Adobe Analytics 术语的扩展术语表。

| 术语 | 描述 | 文档链接 |
| --- | --- | --- |
| Prop（自定义流量） | 用于逐页跟踪网站流量活动的维度。Prop 不会在页面之间持续保留。流量变量的关键应用： <ul> <li>简单计数以查找“最受欢迎”的特定值</li> <li>了解用户如何寻访您的网站。</li> </ul> <br>流量变量的示例：页面名称、网站区域、浏览器 | [Prop](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar（自定义转化） | 在您自定义的时间段内持续保留的维度。过期选项包括事件过期、访问过期、或 X 日过期，应由将对该变量执行的分析类型驱使。<br>eVar 和 prop 之间的主要区别： <ul> <li>prop 通常用于路径分析，因为持久性会被删除。</li> <li>eVar 通常用于转化分析。</li> </ul> <br>转化变量的示例：内部搜索词、内部促销活动、外部促销活动 (s.campaign) | [eVar](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| 事件/指标 (s.events) | 用于测量我们希望访客在我们的网站上采取的关键行动的指标。事件有 3 种类型：计数器、数值和货币。事件在被添加到转化变量报表 (eVar) 时是最有用的。eVar 提供所发生情况的质量信息，事件则提供所发生情况的数量信息。<br>eVar 和事件之间的主要区别： <ul> <li>eVar 可告诉我们，什么人、什么事情或什么内容影响了转化</li> <li>事件可测量有多少转化发生</li> </ul> <br>转化事件的示例：订单数、应用程序启动数、潜在客户数、收入。 | [事件](/help/admin/admin/c-success-events/success-event.md) |
| 组件 | 可以拖放到项目中的维度、指标、区段和时间粒度（日期范围）。 | [组件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| 维度 | eVar、prop、分类和标准 Adobe 收集值的集合。 | [维度](/help/components/dimensions/overview.md) |
| 指标 | 已实施事件和计算指标的集合。 | [指标](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| 计算指标 | 能够从通过实施捕获的现有指标中派生自定义指标。 | [计算指标](/help/components/c-calcmetrics/cm-overview.md) |
| 区段 | 能够生成、管理和共享强大而集中的受众区段，并将其应用于您的 Analytics 报表。区段在各 Analytics 产品间共享，还可在整个 Experience Cloud 中共享。 | [区段划分](/help/components/segmentation/seg-home.md) |
| 时间（日期范围） | 能够将日期过滤到任何时间段并创建可在分析中重用的自定义日期范围。 | [日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| 可视化图表 | 丰富的视觉效果有助于使项目中的数据变得生动。 | [可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| 管理分析 | 能够限制可在项目或虚拟报表包中访问的组件。 | [VRS 策划](/help/components/vrs/vrs-components.md) <br> [项目策划](/help/analyze/analysis-workspace/curate-share/curate.md) |

## 关键报表

| 报表 | 描述 | 文档链接 |
| --- | --- | --- |
| 完整维度/报表列表 | Adobe Analytics 中所有可用维度/报表的定义。 | [维度](/help/components/dimensions/overview.md) |
| Advertising Analytics | 在 Adobe Analytics 中并排分析所有 Google 和 Bing 付费搜索数据。通过该集成创建的维度包括广告平台、关键词、匹配类型等。创建的指标包括 AMO 展示次数、AMO 点击次数、AMO 成本、平均位置和平均质量分数。 | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | 通过 AAM 中用户的受众成员资格来丰富入站 Analytics 点击量。您可以将诸如人口统计信息（如性别或收入水平）、心理统计信息（如兴趣和爱好）、CRM 数据和广告展示数据之类的 AAM 受众数据合并到任何 Analytics 工作流程中。通过此集成创建的维度包括受众 ID 和受众名称。 | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| 归因 IQ | 使您可了解如何在整个客户历程中开展有意义的互动，如何智能识别可将客户引导至目标结果的拐点，以及如何有效地优化营销活动。模型包括：首次联系、最近联系、线性、参与、J 型、反向 J 型、U 型、同一联系、自定义和时间衰减。 | [归因 IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| 异常检测 | 确定给定的指标相对于以前的数据发生了什么变化的一种统计方法。默认情况下，Analysis Workspace 中所有趋势可视化图表的异常检测处于打开状态。 | [异常检测](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| 贡献分析 | 通过对您有权访问的每个指标和维度运行自动分析，了解发生异常的“原因”。 | [贡献分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| 同类群组分析 | 同类群组是指一组在特定期限内共享相同特性的人员。同类群组分析有助于分析用户的维系率和流失率。 | [同类群组分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| 客户历程报表 | 显示有关用户浏览您的网站或应用程序的路径的信息。可以在 Analysis Workspace 中使用 Prop、eVar 和事件进行此类分析。 | [Analysis Workspace 流失](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Analysis Workspace 流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Reports and Analytics 路径](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| 营销渠道 | 一种报表，可帮助您了解哪些外部渠道驱使用户访问您的网站，以及哪些内容可最有效地促使转化。提供首次和最近联系属性视图。这是 Adobe Analytics 中的首选外部流量源报表（而非促销活动或流量源），因为通过它可以最全面地了解付费和免费渠道。 | [营销渠道](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| 移动设备 | 显示有关从移动设备或平板电脑访问的网站的信息。 | [移动设备报表](/help/components/dimensions/mobile-dimensions.md) |
| 移动设备应用程序 | 显示与您的移动设备应用程序相关的基本使用信息。只要我们的 SDK 得以实施并且报表处于开启状态，这些报表即可供您使用。此外，Adobe Mobile Services 还创建了一个单独的移动设备应用程序界面，它提供更加全面的应用程序数据，从而允许您了解和改进应用程序的用户参与。在[此处](https://mobilemarketing.adobe.com)访问该界面。 | [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| 产品 | 识别单个产品和产品组（类别）对各项转化指标（如收入或结账）的贡献情况。 | [产品报表](/help/components/dimensions/product.md) |
| 区段比较 | 通过自动分析您有权访问的每个指标和维度，发现各区段之间的最显著统计学差异。 | [区段比较](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| 网站内容报表 | 显示的信息包括网站上哪些页面和区域最为活跃及哪些服务器使用率最高。 | [网站内容报表](/help/components/dimensions/page.md) |
| 网站指标报表 | 显示有关您的网站的数量信息，例如独特访客数、订单数、收入等。每个指标都可置于其他基于项目的报表中。 | [网站指标报表](/help/components/metrics/overview.md) |
| 访客资料 | 一种报表，可按不同资料类别（包括国家/地区、州、邮政编码及域）来显示客户的购买模式。 | [访客资料](/help/components/dimensions/language.md) |
| 访客维系 | 显示有关客户忠诚度的信息，例如访客回访您的网站的次数和频率。 | [访客维系](/help/components/dimensions/customer-loyalty.md) |
| 项目链接、共享和计划 | 在 Analytics 界面中保存和/或与其他人共享您工作的方法。 | [发送和计划文件](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## 关键指标 {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 指标名称 | 定义 | 文档链接 |
| --- | --- | --- |
| 完整指标列表 | Adobe Analytics 中所有指标的定义。 | [指标概述](/help/components/metrics/overview.md) |
| 独特访客 | 在指定时段内访问网站的非重复访客数量。 | [独特访客](/help/components/metrics/unique-visitors.md) |
| 访问 | 表示一系列的页面查看操作。访问在访客首次查看网站上的页面时开始，在处于非活动状态 30 分钟后结束。 | [访问](/help/components/metrics/visits.md) |
| 页面查看次数 | 访客查看您网站上的页面时即发生页面查看。 | [页面查看次数](/help/components/metrics/page-views.md) |
| 实例 | 定义变量的次数。每当 Adobe Analytics 发现变量中有值时，实例数就会在相应的报表中递增 1。 | [实例](/help/components/metrics/instances.md) |
| 发生次数 | 定义或保留变量的次数。 | [发生次数](/help/components/metrics/occurrences.md) |

## 导入选项 {#concept_7C6DF03B5F9149E2A77F36C739432059}

| 选项 | 描述 | 文档链接 |
| --- | --- | --- |
| 分类导入器 | 通过浏览器或 FTP 上载导入与已捕获维度对应的元数据。相对于规则生成器的手动方法。 | [分类导入器](/help/components/classifications/importer/c-working-with-saint.md) |
| 规则生成器 | 根据用户定义的规则，自动创建维度的元数据分类。 | [分类规则生成器](/help/components/classifications/crb/classification-rule-builder.md) |
| 客户属性 | 上传到 Experience Cloud 以用于 Adobe Analytics 和 Adobe Target 的 CRM 数据。 | [客户属性](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/customer-attributes/attributes.html) |
| 数据源 | 根据维度或只是按天将离线指标导入到 Analytics。 | [数据源](/help/import/c-data-sources/datasrc-home.md) |
| Adobe Exchange Data Connectors | 请参阅 [Analytics 工具](/help/import/data-connectors/data-connectors-eol.md) |  |
| 本机集成 | Audience Analytics 和 Advertising Analytics。 | 请参阅“关键报表”部分。 |

## 导出选项 {#concept_C62B688E259141CF92C048E8110464BE}

| 选项 | 描述 | 文档链接 |
| --- | --- | --- |
| UI 下载和计划 | 从 Analysis Workspace 中以 CSV 或 PDF 格式导出数据 | [下载 PDF 或 CSV 文件](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | 请参阅 Analytics 工具。 |  |
| Analytics API | 创建您自己的自定义 Analytics 数据查询。 | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| data warehouse | 请参阅 Analytics 工具。 |  |
| Analytics 数据馈送 | 从 Analytics 获取数据的最精细方法。设置来自 Analytics 的点击级别馈送。 | [Analytics 数据馈送](/help/export/analytics-data-feed/data-feed-overview.md) |

## 数据收集和验证 {#concept_E07350D4CA5047DAA7D81F762F29606A}

| 方法/资源 | 描述 | 文档链接 |
| --- | --- | --- |
| 开发人员资源 | 文档概述了可用于收集所有可用平台（Web、移动设备应用程序、视频、Flash 等）间 Analytics 数据的库 | [开发人员文档](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| 实施指南 | 有关数据收集变量的说明，以及有关在 JavaScript 中实施数据收集代码的详细信息。 | [实施指南](/help/implement/home.md) |
| App Measurement (s_code) | 全局变量管理 | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| 应用程序 SDK | 包含应用程序配置文件预填充版本的自定义包。 | <ul><li>[iOS](https://docs.adobe.com/content/help/zh-Hans/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/zh-Hans/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM 和 Adobe Launch | 请参阅 Analytics 工具。 |  |
| VISTA | 允许您在收集数据时应用服务器端逻辑来更改或划分数据。 | [VISTA 规则](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| 处理规则 | 能够在 Analytics UI 中设置、修改和复制变量，以更改收集的数据。 | [处理规则](/help/admin/admin/c-processing-rules/processing-rules.md) |
| 调试器选项 | 有几个调试器和数据包探查器可用于帮助验证您的实施，包括 Adobe Experience Cloud 调试器。 | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=zh-Hans) |
| 数据插入 API | 数据插入 API 提供了一种机制，可用于收集服务器端数据并将这些数据提交到 Experience Cloud 服务器。服务器端数据收集仅基于 Web 浏览器请求和 Web 服务器响应来收集数据，而不是在每个网页上使用 JavaScript 信标将访客数据传输到 Experience Cloud 服务器。 | [使用 POST 实施 Adobe Analytics 数据插入 API 的步骤](https://helpx.adobe.com/cn/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
