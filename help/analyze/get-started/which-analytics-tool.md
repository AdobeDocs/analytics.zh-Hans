---
description: 本帮助页面包含每个 Adobe Analytics 工具的推荐使用案例。应该按照工具的列出顺序来考虑使用哪个工具。如果某个工具无法满足需求，请考虑切换到下一个工具。
title: 我应该使用哪种 Adobe Analytics 工具？
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: ht
source-wordcount: '1122'
ht-degree: 100%

---

# 我应该使用哪种 Adobe Analytics 工具？

本帮助页面包含每个 Adobe Analytics 工具的推荐使用案例。应该按照工具的列出顺序来考虑使用哪个工具。如果某个工具无法满足需求，请考虑切换到下一个工具。

有关 Adobe Analytics 产品比较的更多信息，请参阅[Analytics 产品比较](/help/analyze/get-started/analytics-product-comparison.md)。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [工具比较](https://video.tv.adobe.com/v/30267?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


## Adobe Analytics 报告用户界面 {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** 应该是您的首选用户界面，可满足您所有的报告与分析需求。Adobe 会继续投入人力和物力坚持每月发布此产品的更新。如果有任务无法在 Analysis Workspace 中完成，您可以考虑使用下面列出的其他界面。**

通过 **[Adobe Analytics 功能板](/help/analyze/mobile-app/home.md)**，用户可移动访问直观的记分卡。记分卡是关键量度和其他组件的集合，这些组件以平铺布局显示，您可以点击它们以获取更详细的划分和趋势报表。iOS 和 Android 操作系统均支持移动设备应用程序。

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** 是 Microsoft Excel 的一个插件，可在 Mac、Windows 和网络浏览器上运行。通过它，可从 Adobe Analytics 数据构建自定义的请求，并可将其插入 Excel 工作表。请求可动态引用工作表中的单元格，并且您可更新和自定义 Report Builder 展示数据的方式。

**[旧版 Report Builder](/help/analyze/legacy-report-builder/home.md)** 是 Microsoft Excel 的一个插件，仅在 Windows 上运行。通过它，可从 Adobe Analytics 数据构建自定义的请求，并可将其插入 Excel 工作表。请求可动态引用工作表中的单元格，并且您可更新和自定义 Report Builder 展示数据的方式。

**[Activity Map](/help/analyze/activity-map/overview.md)** 是 Adobe Analytics 中的一项功能，它用视觉方式展示用户使用网页和移动应用程序的情况。它使营销人员和分析人员可跟踪和分析用户交互，如点击、悬停和滚动行为。

## 将数据导入到 Adobe Analytics 中 {#import}

**[分类](/help/components/classifications/classifications-overview.md)**&#x200B;应用于以下情况：

* 要将元数据与某个收集值（eVar、prop、营销渠道）相关联时。Adobe 建议使用[分类集](/help/components/classifications/sets/overview.md)。分类规则生成器和分类导入程序是将分类数据引入 Adobe Analytics 的传统方法。

**[数据源](/help/import/data-sources/overview.md)**&#x200B;的使用说明：

* 适用于要将离线数据永久写入 Adobe Analytics 的情况
* 选项:
   * 摘要：按日期或有限维度显示简单数据上传
   * 交易 ID：数据上传将在线端点与离线数据连接起来，并将导入的数据与访客在线捕获的快照完全关联（例如，在线完成并离线返回的订单）

**[Adobe Exchange 集成](https://www.adobeexchange.com/experiencecloud.html)**&#x200B;应该用于：

* 与已建立支持的 Adobe Analytics 连接的第三方提供商开展业务的情况。集成应用程序一般不断自动地将摘要级别的数据永久纳入 Adobe Analytics。

**[批量数据插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* “批量数据插入 API”接受包含事件数据在内的 CSV 格式的文件，其中每行有一个事件。对于任何需要服务器端代码或者否则就无法使用 AppMeasurement 或 Web SDK 进行数据收集的实施，Adobe 建议使用“批量插入 API”。

以下情况下应使用&#x200B;**[数据插入 API（旧版）](/help/import/c-data-insertion-api/c-data-insertion-api.md)**：

* 当您需要将数据导入 Adobe Analytics 且无法使用 AppMeasurement、Web SDK 或“批量数据插入 API”时。

应在以下情况下使用&#x200B;**[客户属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hans)**：

* 适用于您在客户关系管理 (CRM) 数据库中捕获了企业客户数据，并希望将该数据上传到 Experience Cloud 的情况。
* 适用于要在 Analytics 中使用 CRM 数据进行更深入的分析，或要在 Adobe Target 中将该数据作为定位条件的情况。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** 的使用说明：

* 适用于要将诸如人口统计信息（如性别或收入水平）、心理统计信息（如兴趣和爱好）、CRM 数据或广告展示数据之类的 Adobe Audience Manager 受众数据合并到任何 Analytics 工作流程中的情况。
* 适用于希望上传的 CRM 数据基于时间（因为此集成会按点击将新信息发送给 Analytics）的情况。

## 从 Adobe Analytics 导出数据 {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** 的使用说明：

* 适用于工作区的自定义布局选项有限的情况（在 Excel 的限制范围内，Report Builder 可执行任何操作）。
* 用于将用户输入的内容或离线数据源（展示次数、成本）松散绑定到 Adobe 数据。更永久的绑入数据解决方案是数据源（请参阅“将数据导入到 Analytics”）。
* 用于合并不同维度报表中的数据（例如，合并促销活动展示次数报表和促销活动点击转化报表）。
* 通过汇总或并排显示在同一表格中，将不同报告包的数据合并在一起。
* 适用于需要通过计划实现自动化的情况（XLSX、XLSM、CSV、PDF、TXT、XML、MHT）。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** 的使用说明：

* 用于访问隐藏在 UI 中的变量，包括 IP 地址、Experience Cloud ID、Analytics 访客 ID、页面 URL
* 用于访问比 UI 更细粒度的数据（非规范化的表视图）
* 用于下载适用于数据透视表输入格式的数据
* 适用于客户端要将 Adobe 数据输入第三方数据可视化工具的情况（稍微汇总，不是点击级别）
* 用于在 Adobe Analytics 中遇到“低流量”的情况下访问所有独特维度项目

应使用 **[Analytics 数据馈送](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**：

* 用于利用 Adobe 可提供的最细粒度的数据馈送（访客 ID、点击量）
* 适用于客户端要在 Adobe 可发送的最细粒度级别发送客户端数据库中存储的 Adobe 数据的情况。
* 适用于客户端要开发商智能 (BI) 工具或将点击级别的 Adobe 数据导入第三方工具的情况.

**[报表 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** 适用于其他可视化选项无法满足您需求的情况。其中包括以下 3 个 API 选项：

* **经过完全处理**：适用于您需要功能丰富的数据（包括访问量、访客量和区段）的情况。这是典型的 Analytics UI 汇总数据，有效期约为 30-90 分钟。可以通过 Report Builder 使用。
* **实时**：适用于要延迟几秒查看若干量度和维度的情况。这是经过部分处理的有限汇总数据，有效期约为 30 秒。其中包含最受欢迎、获胜方和失败方的独特算法。可以通过 Report Builder 使用。
* **[!UICONTROL 实时流]**：适用于要在几秒内收集经过部分处理的点击级别的 Analytics 数据流。这是经过部分处理的数据，有效时间在大约 30 秒之内。仅适用于 Analytics Premium。要求通过某种方式显示数据，通常是通过参与工程技术服务。

## 自定义解决方案 {#custom-solutions}

应在以下情况使用工程技术服务：

* 其他 Adobe 工具无法满足您的需求。
* 希望获得自定义体验。
* 希望获得完全自动化的解决方案。
* 希望使用许多设备。
* 拥有多个数据源。
* 您的数据 ETL（提取-转换-加载）要求十分复杂。
* 希望自定义品牌。
* 希望可视化 [!UICONTROL Analytics 实时流]。
