---
description: 此帮助页包含每个Adobe Analytics工具的推荐用例。 工具应按照列出的顺序进行考虑。 如果某个工具无法满足此需要，请移至下一个工具以供考虑。
title: 我应该使用哪种 Adobe Analytics 工具？
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
TQID: https://experienceleague.adobe.com/xk485fKU7Q2DeZIYaTtN-a4JKnyVamAygW03z7ffAOk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1175
ht-degree: 68%

---

# 我应该使用哪种 Adobe Analytics 工具？

此帮助页包含每个Adobe Analytics工具的推荐用例。 工具应按照列出的顺序进行考虑。 如果某个工具无法满足此需要，请移至下一个工具以供考虑。

有关 Adobe Analytics 产品比较的更多信息，请参阅[Analytics 产品比较](/help/analyze/get-started/analytics-product-comparison.md)。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [工具比较](https://video.tv.adobe.com/v/30267?captions=chi_hans&quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


## Adobe Analytics 报告用户界面 {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** 应该是您的首选用户界面，可满足您所有的报告与分析需求。 Adobe 会继续投入人力和物力坚持每月发布此产品的更新。 如果有任务无法在 Analysis Workspace 中完成，您可以考虑使用下面列出的其他界面。**

通过 **[Adobe Analytics 功能板](/help/analyze/mobile-app/home.md)**，用户可移动访问直观的记分卡。 记分卡是关键量度和其他组件的集合，这些组件以平铺布局显示，您可以点击它们以获取更详细的划分和趋势报表。 iOS 和 Android 操作系统均支持移动设备应用程序。

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** 是 Microsoft Excel 的一个插件，可在 Mac、Windows 和网络浏览器上运行。 通过它，可从 Adobe Analytics 数据构建自定义的请求，并可将其插入 Excel 工作表。 请求可动态引用工作表中的单元格，并且您可更新和自定义 Report Builder 展示数据的方式。

**[旧版 Report Builder](/help/analyze/legacy-report-builder/home.md)** 是 Microsoft Excel 的一个插件，仅在 Windows 上运行。 通过它，可从 Adobe Analytics 数据构建自定义的请求，并可将其插入 Excel 工作表。 请求可动态引用工作表中的单元格，并且您可更新和自定义 Report Builder 展示数据的方式。

**[Activity Map](/help/analyze/activity-map/overview.md)** 是 Adobe Analytics 中的一项功能，它用视觉方式展示用户使用网页和移动应用程序的情况。 它使营销人员和分析人员可跟踪和分析用户交互，如点击、悬停和滚动行为。

## 将数据导入到 Adobe Analytics 中 {#import}

**[分类](/help/components/classifications/classifications-overview.md)**&#x200B;应用于以下情况：

* 要将元数据与某个收集值（eVar、prop、营销渠道）相关联时。 Adobe 建议使用[分类集](/help/components/classifications/sets/overview.md)。 分类规则生成器和分类导入程序是将分类数据引入 Adobe Analytics 的传统方法。

**[数据源](/help/import/data-sources/overview.md)**&#x200B;的使用说明：

* 适用于要将离线数据永久写入 Adobe Analytics 的情况
* 选项:
   * 摘要：按日期或有限维度显示简单数据上传
   * 交易 ID：数据上传将在线端点与离线数据连接起来，并将导入的数据与访客在线捕获的快照完全关联（例如，在线完成并离线返回的订单）

**[Adobe Exchange 集成](https://www.adobeexchange.com/experiencecloud.html)**&#x200B;应该用于：

* 与已建立支持的 Adobe Analytics 连接的第三方提供商开展业务的情况。 集成应用程序一般不断自动地将摘要级别的数据永久纳入 Adobe Analytics。

**[批量数据插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* “批量数据插入 API”接受包含事件数据在内的 CSV 格式的文件，其中每行有一个事件。 对于任何需要服务器端代码或者否则就无法使用 AppMeasurement 或 Web SDK 进行数据收集的实施，Adobe 建议使用“批量插入 API”。

以下情况下应使用&#x200B;**[数据插入 API（旧版）](/help/import/c-data-insertion-api/c-data-insertion-api.md)**：

* 当您需要将数据导入 Adobe Analytics 且无法使用 AppMeasurement、Web SDK 或“批量数据插入 API”时。

应在以下情况下使用&#x200B;**[客户属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hans)**：

* 如果您在客户关系管理(CRM)数据库中捕获到企业客户数据，并希望将该数据上传到CX Enterprise。
* 如果要使用CRM数据在Analytics中进行更深入的分析，或希望在Adobe Target中用作定位标准。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** 的使用说明：

* 适用于要将诸如人口统计信息（如性别或收入水平）、心理统计信息（如兴趣和爱好）、CRM 数据或广告展示数据之类的 Adobe Audience Manager 受众数据合并到任何 Analytics 工作流程中的情况。
* 适用于希望上传的 CRM 数据基于时间（因为此集成会按点击将新信息发送给 Analytics）的情况。

## 从Adobe Analytics导出数据 {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** 的使用说明：

* 如果Workspace的自定义布局选项受限于（在Report Builder中，在Excel的限制内可进行任何操作）。
* 用于将用户输入的内容或离线数据源（展示次数、成本）松散绑定到 Adobe 数据。 更永久的绑入数据解决方案是数据源（请参阅“将数据导入到 Analytics”）。
* 用于合并不同维度报表中的数据（例如，合并促销活动展示次数报表和促销活动点击转化报表）。
* 通过汇总或并排显示在同一表格中，将不同报告包的数据合并在一起。
* 适用于需要通过计划实现自动化的情况（XLSX、XLSM、CSV、PDF、TXT、XML、MHT）。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** 的使用说明：

* 用于访问隐藏在 UI 中的变量，包括 IP 地址、Experience Cloud ID、Analytics 访客 ID、页面 URL
* 访问比UI更细粒度的数据（非标准化表视图）
* 以适合数据透视表输入的格式下载数据
* 如果客户希望将Adobe数据输入到第三方数据可视化工具中（稍微摘要一下，而不是点击级别）
* 用于在 Adobe Analytics 中遇到“低流量”的情况下访问所有独特维度项目

应使用 **[Analytics 数据馈送](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**：

* 利用我们可以提供的最细粒度的数据馈送（访客ID、点击）。
* 如果客户端希望将Adobe数据存储到客户端数据库中，我们可以以最精细的粒度级别发送。
* 如果客户希望开发Business Intelligence (BI)工具或将点击级别的Adobe数据输入到第三方工具。

**[报表 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** 适用于其他可视化选项无法满足您需求的情况。 这3个API选项包括：

* **完全处理**：需要功能丰富的数据（包括访问次数、访客数和区段）时。 这是典型的Analytics UI汇总数据，可在约30-90分钟内提供。 可以通过Report Builder使用。
* **实时**：适用于要延迟几秒查看若干量度和维度的情况。 这是有限的、部分处理的汇总数据，在约30秒内可用。 包括最受欢迎、获胜方和失败方的独特算法。 可以通过Report Builder使用。
* **[!UICONTROL 实时流]**：适用于要在几秒内收集经过部分处理的点击级别的 Analytics 数据流。 这是部分处理的数据，在约30秒内可用。 仅适用于Analytics Premium。 需要某种可视化数据的方法，通常通过工程技术服务项目来实现。

## 自定义解决方案 {#custom-solutions}

应在以下情况使用工程技术服务：

* 其他 Adobe 工具无法满足您的需求。
* 您需要自定义体验。
* 您需要一个完全自动化的解决方案。
* 您希望访问许多设备。
* 您有多个数据源。
* 您具有复杂的数据ETL（提取 — 转换 — 加载）要求。
* 您需要自定义品牌。
* 要可视化[!UICONTROL Analytics实时流]。
