---
description: 本帮助页面包含每个 Adobe Analytics 工具的推荐使用案例。应该按照工具的列出顺序来考虑使用哪个工具。如果某个工具无法满足需求，请考虑切换到下一个工具。
title: 我应该使用哪种 Adobe Analytics 工具？
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: ht
source-wordcount: '1227'
ht-degree: 100%

---

# 我应该使用哪种 Adobe Analytics 工具？

本帮助页面包含每个 Adobe Analytics 工具的推荐使用案例。应该按照工具的列出顺序来考虑使用哪个工具。如果某个工具无法满足需求，请考虑切换到下一个工具。

有关 Adobe Analytics 产品比较的更多信息，请参阅[Analytics 产品比较](/help/analyze/get-started/analytics-product-comparison.md)。

以下是一段比较各种 Adobe Analytics 工具的视频：

>[!VIDEO](https://video.tv.adobe.com/v/27220/?quality=12)

## Adobe Analytics 报表用户界面 {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** 应该是您的首选用户界面，可满足您所有的报告与分析需求。Adobe 会继续投入人力和物力坚持每月发布此产品的更新。如果有任务无法在 Analysis Workspace 中完成，您可以考虑使用下面列出的其他界面。**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)** 的使用说明：

* 适用于需要访问更易导航的预构建报表的初学用户。
* 用于访问 UI 中的实时数据。
* 用于设置日程表事件。
* 用于设置目标。
* 用于访问有关“视频时段”和“观看者流失率”的独特的视频可视化图表。

>[!IMPORTANT]
>
>自 **2023 年 12 月 31 日**&#x200B;起，Adobe 决定中断 Reports &amp; Analytics 及其随附的报表和功能。到时候，Reports &amp; Analytics 及其所有报表和计划都将停止工作。支持 Reports &amp; Analytics 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。在 Analysis Workspace 中提供了 Reports &amp; Analytics 的大部分功能。自 2015 年发布 Analysis Workspace 以来，Reports &amp; Analytics 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。本通知解释了生命周期结束的过程。

**[Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html?lang=zh-Hans)** 的使用说明：

* 适用于预测统计模型（倾向评分、群集、关联等）。
* 适用于延迟分析（事件前/后的时间）。
* 用于识别和导出 Adobe Experience Cloud 中的复杂区段。

>[!IMPORTANT]
>
>详细阅读 Data Workbench 的[生命周期终止公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hans)。


## 将数据导入到 Adobe Analytics 中 {#import}

**[分类](/help/components/classifications/c-classifications.md)**&#x200B;的使用说明：

* 适用于要将元数据与收集值（eVar、prop、营销渠道）关联的情况
* 选项:

   * 规则生成器：可在为变量（例如分隔值）收集可预测格式的值时使用。通过这种方法，您只需设置一次规则，然后就“万事无忧”了。
   * 浏览器导入器：可在没有可预测的值或需要一次性更新有限的值列表时使用。此方法要求您持续监控分类的新值。

**[数据源](/help/import/data-sources/overview.md)**&#x200B;的使用说明：

* 适用于要将离线数据永久写入 Adobe Analytics 的情况
* 选项:

   * 摘要：按日期或有限维度显示简单数据上传
   * 交易 ID：数据上传将在线端点与离线数据连接起来，并将导入的数据与访客在线捕获的快照完全关联（例如，在线完成并离线返回的订单）
   * 完全处理：像处理 Adobe 服务器收集的点击一样处理带有时间戳的数据源。例如，直接将数据插入访客历程。

**[Adobe Exchange 集成](https://www.adobeexchange.com/experiencecloud.html)**&#x200B;应该用于：

* 与已建立支持的 Adobe Analytics 连接的第三方提供商开展业务的情况。集成应用程序一般不断自动地将摘要级别的数据永久纳入 Adobe Analytics。

**[数据插入 API](/help/import/c-data-insertion-api/c-data-insertion-api.md)** 的使用说明：

* 适用于需要将数据上传到 Adobe Analytics，但无法使用 Adobe AppMeasurement 或移动 SDK 代码的情况。

**[批量数据插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* “数据插入 API”和“批量数据插入 API”都可以把从服务器端收集的数据提交到 Adobe Analytics。每次生成事件时都将调用“数据插入 API”。“批量数据插入 API”接受包含事件数据在内的 CSV 格式的文件，其中每行有一个事件。如果您正在实施新的服务器端收集，我们建议您使用“批量数据插入 API”。

应在以下情况下使用&#x200B;**[客户属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hans)**：

* 适用于您在客户关系管理 (CRM) 数据库中捕获了企业客户数据，并希望将该数据上传到 Experience Cloud 的情况。
* 适用于要在 Analytics 中使用 CRM 数据进行更深入的分析，或要在 Adobe Target 中将该数据作为定位条件的情况。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** 的使用说明：

* 适用于要将诸如人口统计信息（如性别或收入水平）、心理统计信息（如兴趣和爱好）、CRM 数据或广告展示数据之类的 Adobe Audience Manager 受众数据合并到任何 Analytics 工作流程中的情况。
* 适用于希望上传的 CRM 数据基于时间（因为此集成会按点击将新信息发送给 Analytics）的情况。

## 从 Adobe Analytics 导出数据 {#export}

**[Report Builder](/help/analyze/report-builder/home.md)** 的使用说明：

* 适用于工作区的自定义布局选项有限的情况（在 Excel 的限制范围内，Report Builder 可执行任何操作）。
* 用于将用户输入的内容或离线数据源（展示次数、成本）松散绑定到 Adobe 数据。用于将数据关联起来的更为永久的解决方案是数据源（请参阅“将数据导入 Analytics”） 
* 用于将不同维度报表中的数据合并起来（例如，将促销活动展示次数报表和促销活动点击对话报表合并起来）。
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
