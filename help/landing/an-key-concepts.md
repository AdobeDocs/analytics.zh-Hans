---
description: 此部分包含 Adobe Analytics 的关键概念，有关该概念的简要描述，以及具有该主题额外详细信息的特定文档链接。
seo-description: 此部分包含 Adobe Analytics 的关键概念，有关该概念的简要描述，以及具有该主题额外详细信息的特定文档链接。
seo-title: Adobe Analytics - 关键概念
title: Adobe Analytics - 关键概念
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Adobe Analytics - 关键概念

此部分包含 Adobe Analytics 的关键概念，有关该概念的简要描述，以及具有该主题额外详细信息的特定文档链接。

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 产品 | 描述 | 文档链接 |
|--- |--- |--- |
| Analysis Workspace | 用于构建强大的自定义分析项目和实现洞察大众化的浏览器解决方案。 与Reports &amp; Analytics相比，报告更灵活 | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Reports &amp; Analytics（以前称为 SiteCatalyst） | 用于报告和分析的浏览器解决方案。 Analytics 包中的初学者工具。 | [Reports &amp; Analytics主页](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Excel插件，可让您从Adobe Analytics数据构建自定义请求，并使用Microsoft excel对其进行可视化。 | [Report Builder主页](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Ad Hoc Analysis（以前称为 Discover） | 用于高级数字分析的基于Java的工具。 | [临时分析主页](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench（以前称为 Insight） | 旨在收集、处理、分析与可视化来自多个渠道间在线和离线客户交互的数据。 | [Data Workbench 客户端](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Data Warehouse | 用于存储和自定义报表的、未经处理的原始数据，您可通过过滤数据运行它。无点击级别。 | [数据仓库主页](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | 可以在整个 Adobe Experience Cloud 范围内将移动设备应用程序的移动营销功能整合在一起，以便您了解和提高应用程序的用户参与度。 | [Mobile services主页](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors（以前称为Genesis） | 将跟踪数据从第三方应用程序导入Analytics中，以便在一个中心位置实现端到端的性能可视性。 | [数据连接器主页](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| 动态标签管理 (DTM) | 帮助您管理所有网站上的 Analytics、Target 及其他标签，而无需考虑您有多少个域。 | [DTM主页](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | Adobe的新一代网站标签和移动SDK管理功能。 | [Adobe Launch主页](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

单击[此处](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html)，以获取有关 Adobe Analytics 术语的扩展术语表。

| 术语 | 描述 | 文档链接 |
|--- |--- |--- |
| Prop（自定义流量） | 用于跟踪逐页站点流量活动的维度。 Prop 不会在页面之间持续保留。流量变量的关键应用： <ul><li>查找特定值“最受欢迎”的简单计数</li><li>了解用户在网站中的路径 </li></ul><br>流量变量示例：页面名称、站点部分、浏览器</br> | [Prop](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar（自定义转换） | 您自定义的维在一段时间内保留。 过期选项包括事件过期、访问过期、或 X 日过期，应由将对该变量执行的分析类型驱使。<br>eVar和prop之间的主要区别：</br><ul><li>Prop通常用于路径分析，因为会删除持久性。</li><li>eVar通常用于转化分析。</li></ul><br>转换变量示例：内部搜索词、内部促销、外部营销活动(s.campaign)</br> | [eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| 事件／指标(s.events) | 衡量我们希望访客对我们网站采取的关键操作的指标。 事件有 3 种类型：计数器、数值和货币。事件在被添加到转化变量报表 (eVar) 时是最有用的。eVar 提供所发生情况的质量信息，事件则提供所发生情况的数量信息。<br>eVar和事件之间的主要区别：</br><ul><li>eVar告诉我们谁、什么或哪些因素影响了转化</li><li>事件衡量发生转化的次数</li></ul><br>转化事件的示例：订单数、应用程序启动数、潜在客户数、收入。</br> | [事件](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| 组件 | 维度、量度、细分和时间粒度（日期范围），您可以将它们拖放到项目上。 | [组件](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| 维度 | eVar、prop、分类和标准Adobe收集的值的集合。 | [维度](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| 量度 | 已实施事件和计算量度的集合。 | [量度](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| 计算量度 | 能够从通过实施捕获的现有量度中派生自定义量度。 | [计算量度](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| 区段 | 能够生成、管理和共享强大而集中的受众区段，并将其应用于您的 Analytics 报表。区段在各 Analytics 产品间共享，还可在整个 Experience Cloud 中共享。 | [区段划分](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| 时间（日期范围） | 能够将日期筛选到任何时间段并创建可在分析中重复使用的自定义日期范围。 | [日期范围](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| 可视化 | 丰富的视觉元素有助于让项目中的数据栩栩如生。 | [可视化](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| 管理分析 | 能够限制在项目或虚拟报告套件中可访问的组件。 | [VRS特选](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[项目特选](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[比较](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## 关键报告

| 报表 | 描述 | 文档链接 |
|--- |--- |--- |
| 完整维度/报表列表 | Adobe Analytics 中所有可用维度/报表的定义。 | [维度](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html) |
| Advertising Analytics | 在Adobe Analytics中并排分析所有Google和Bing付费搜索数据。 通过集成创建的维包括广告平台、关键字、匹配类型等。 创建的指标包括AMO印象、AMO点击、AMO成本、平均 位置和平均 质量分数划分。 | [Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | 通过AAM中用户的受众会员资格丰富入站分析点击量。 您可以将AAM受众数据(如人口统计信息（如性别或收入水平）、心理信息（如兴趣和爱好）、CRM数据和广告印象数据)并入任何Analytics工作流程。 通过此集成创建的维是受众ID和受众名称。 | [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| 归因 IQ | 使您能够了解在整个客户旅程中进行有意义的互动的方式，智能地识别引导客户实现目标的拐点，从而有效地优化营销计划。 模型包括第一个、最后一个、线性、参与度、j形、逆j形、u形、相同触控、定制和时间衰减。 | [归因 IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| 异常检测 | 一种统计方法，用于确定给定度量相对于先前数据的变化方式。 默认情况下，Analysis Workspace中所有趋势可视化的AD处于打开状态。 | [异常检测](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| 贡献分析 | 通过对您有权访问的每个指标和维度进行自动分析，探索异常发生的“原因”。 | [贡献分析](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| 同类群组分析 | 同期群是指在指定时间段内共享共同特征的一组人。 群组分析有助于分析用户的保留和流失情况。 | [同类群组分析](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| 客户旅程报告 | 显示有关用户浏览您的站点或应用程序的路径的信息。 Prop、eVar和事件可用于Analysis Workspace中的此分析。 | [Analysis Workspace流失](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[分析Workspace流](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[报告和分析路径](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| 营销渠道 | 一种报表，可帮助您了解哪些外部渠道驱使用户访问您的网站，以及哪些内容可最有效地促使转化。提供首次和最近联系属性视图。这是 Adobe Analytics 中的首选外部流量源报表（而非促销活动或流量源），因为通过它可以最全面地了解付费和免费渠道。 | [营销渠道](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| 移动设备 | 显示有关从移动设备或平板电脑访问的网站的信息。 | [移动报告 | (https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| 移动设备应用程序 | 显示与您的移动设备应用程序相关的基本使用信息。只要我们的 SDK 得以实施并且报表处于开启状态，这些报表即可供您使用。此外，Adobe Mobile Services 还创建了一个单独的移动设备应用程序界面，它提供更加全面的应用程序数据，从而允许您了解和改进应用程序的用户参与。在此处访问 [界面](https://mobilemarketing.adobe.com)。 | [Adobe Mobile 服务](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | 产品 | 识别单个产品和产品组（类别）对各项转化量度（如收入或结账）的贡献情况。 | [产品报告](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| 区段比较 | 通过自动分析您有权访问的每个指标和维度，发现细分之间最显着的统计差异。 | [区段比较](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| 站点内容报告 | 显示的信息包括网站上哪些页面和区域最为活跃及哪些服务器使用率最高。 | [站点内容报告](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| 站点指标报告 | 显示有关您的网站的数量信息，例如独特访客数、订单数、收入等。每个量度都可置于其他基于项目的报表中。 | [站点指标报告](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| 访客资料 | 一种报表，可按不同资料类别（包括国家/地区、州、邮政编码及域）来显示客户的购买模式。 | [访客资料](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| 访客维系 | 显示有关客户忠诚度的信息，例如访客回访您的网站的次数和频率。 | [访客维系](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| 项目链接、共享和计划 | 在 Analytics 界面中保存和/或与其他人共享您工作的方法。 | [发送和计划文件](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 量度名称 | 定义 | 文档链接 |
|---|---|---|
| 完整量度列表 | Adobe Analytics 中所有量度的定义。 | [量度概述](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| 独特访客 | 在指定时段内访问网站的非重复访客数量。 | [独特访客](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| 访问 | 表示一系列的页面查看操作。访问在访客首次查看网站上的页面时开始，在处于非活动状态 30 分钟后结束。 | [访问](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| 页面查看次数 | 访客查看您网站上的页面时即发生页面查看。 | [页面查看次数](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| 实例 | 定义变量的次数。每当 Adobe Analytics 发现变量中有值时，实例数就会在相应的报表中递增 1。 | [实例](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| 发生次数 | 定义或保留变量的次数。 | [发生次数](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## 导入选项 {#concept_7C6DF03B5F9149E2A77F36C739432059}

| 选项 | 描述 | 文档链接 |
|---|---|---|
| 分类导入器 | 通过浏览器或 FTP 上载导入与已捕获维度对应的元数据。相对于规则生成器的手动方法。 | [分类导入器](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| 规则生成器 | 根据用户定义的规则，自动创建维度的元数据分类。 | [分类规则生成器](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| 客户属性 | 上传到Experience cloud以用于Adobe Analytics和Adobe Target的CRM数据。 | [客户属性](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| 数据源 | 根据维度或按天将离线指标引入Analytics。 | [数据源](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Adobe Exchange Data Connectors | 请参阅 [分析工具](/help/landing/an-key-concepts.md) |  |
| 本机集成 | Audience Analytics和Advertising Analytics。 | 请参阅“关键报告”部分。 |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

| 选项 | 描述 | 文档链接 |
|---|---|---|
| UI下载和计划 | 从Analysis Workspace中以CSV或PDF格式导出数据 | [下载 PDF 或 CSV 文件](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | 请参阅分析工具。 |
| Analytics API | 创建您自己的自定义 Analytics 数据查询。 | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | 请参阅分析工具。 |  |
| Analytics 数据馈送 | 从 Analytics 获取数据的最精细方法。设置来自 Analytics 的点击级别馈送。 | [Analytics 数据馈送](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| 方法/资源 | 描述 | 文档链接 |
|--- |--- |--- |
| 开发人员资源 | 文档概述了可用于收集所有可用平台（Web、移动设备应用程序、视频、Flash 等）间 Analytics 数据的库 | [开发人员文档](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| 实施指南 | 有关数据收集变量的说明，以及有关在 JavaScript 中实施数据收集代码的详细信息。 | [实施指南](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| App Measurement (s_code) | 全局变量管理 | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| 应用程序 SDK | 包含应用程序配置文件预填充版本的自定义包。 | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM和Adobe Launch | 请参阅分析工具。 |  |
| VISTA | 允许您应用服务器端逻辑来在收集数据时更改或细分数据。 | [VISTA 规则](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html) |
| 处理规则 | 能够在Analytics UI中设置、修改和复制变量，以更改收集的数据。 | [处理规则](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| 调试程序选项 | 有几个调试器和数据包嗅探器可用于帮助验证您的实施，包括Adobe Experience cloud调试器。 | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| 数据插入 API | 数据插入API为服务器端数据收集和提交到Experience cloud服务器提供了一种机制。 服务器端数据收集仅根据Web浏览器请求和Web服务器响应收集数据，而不是使用每个网页上的JavaScript信标将访客数据传输到Experience Cloud服务器。 | [使用POST实施Adobe Analytics数据插入API的步骤](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
