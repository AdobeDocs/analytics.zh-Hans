---
description: 本帮助页面包含每个 Adobe Analytics 工具的推荐使用案例。应该按照工具的列出顺序来考虑使用哪个工具。如果某个工具无法满足需求，请考虑切换到下一个工具。
seo-description: 本帮助页面包含每个 Adobe Analytics 工具的推荐使用案例。应该按照工具的列出顺序来考虑使用哪个工具。如果某个工具无法满足需求，请考虑切换到下一个工具。
seo-title: 我应该使用哪个Adobe Analytics工具？
title: 我应该使用哪个Adobe Analytics工具？
uuid: 1179e49d-3cfc-4abd-a8 eb-35c5 ae380 c16
translation-type: tm+mt
source-git-commit: bf9152741507c75e1f92e8d5d515127eadf5d590

---


# 我应该使用哪个Adobe Analytics工具？

本帮助页面包含每个 Adobe Analytics 工具的推荐使用案例。应该按照工具的列出顺序来考虑使用哪个工具。如果某个工具无法满足需求，请考虑切换到下一个工具。

有关 Adobe Analytics 产品比较的详细信息，请转至[此处](../../admin/c-analytics-product-comparison/analytics-product-comparison.md#concept_D9DB9FA42CA04F4C97765B6B31A0005D)。

## Adobe Analytics 报表用户界面 {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)** 应该是您的首选用户界面，可满足您所有的报告与分析需求。Adobe 会继续投入人力和物力坚持每月发布此产品的更新。如果您无法在Analysis Workspace中执行任务，请考虑下面的其他界面。****

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)** 的使用说明：

* 适用于需要访问更易导航的预构建报表的初学用户。
* 可对 A4T 活动展示次数与转化次数进行准确的计数。
* 用于了解 Target 活动 (Analytics for Target/A4T) 的提升度和置信度。
* 用于访问 UI 中的实时数据。
* 用于设置日历事件。
* 用于设置目标。
* 用于查看机器人报表。
* 用于在单个 UI 功能板中查看多个报表包。
* 用于访问独特的视频数据（包括并行查看者、视频时段和视频查看者退出率）的可视化图表。
* 用于在计划报表中使用“发布列表”功能。

**[Mobile Services UI](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)** 的使用说明：

* 适用于需要只查看移动设备应用程序数据的情况。
* 用于管理移动设备应用程序 SDK 的实施。
* 用于设置移动设备广告，例如应用程序内消息、推送消息和位置定位。
* 适用于应用程序数据 (Sunburst) 需要更多交互可视化的情况。
* 用于可视化地图上的目标点。
* 适用于存留期值量度。

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)** 的使用说明：

* 适用于确实需要使用表格生成器功能的情况。例如，a) Analysis Workspace 无法支持您需要构建的内容，b) 您希望能够控制何时重新构建表格，c) 您希望表格记住要应用到所有行的不同划分级别 d) 您希望对量度行手动排序
* 用于导出 50,000 行数据
* 适用于需要以选项卡方式组织项目工作的情况。
* 用于使用网站分析报表（3D 路径报表）。

**[Data Workbench](https://marketing.adobe.com/resources/help/en_US/insight/)** 的使用说明：

* 最灵活的 Analytics 工具选项（针对访客级别和点击级别分析）。
* 用于创建从 CRM 到 POS 和 Web 的在线和离线交互的多渠道数据集。
* 适用于高级属性（基于规则的模型和算法模型）。
* 适用于预测统计模型（倾向评分、群集、关联等）。
* 适用于延迟分析（事件前/后的时间）。
* 用于识别和导出 Adobe Experience Cloud 中的复杂区段。

## 将数据导入 Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[分类](/help/components/c-classifications2/c-classifications.md)**&#x200B;的使用说明：

* 适用于要将元数据与收集值（eVar、prop、营销渠道）关联的情况
* 选项：

   * 规则生成器：可在为变量（例如分隔值）收集可预测格式的值时使用。通过这种方法，您只需设置一次规则，然后就“万事无忧”了。
   * 浏览器导入器：可在没有可预测的值或需要一次性更新有限的值列表时使用。此方法要求您持续监控分类的新值。

**[数据源](/help/import/c-data-sources/datasrc-home.md)**&#x200B;的使用说明：

* 适用于要将离线数据永久写入 Adobe Analytics 的情况
* 选项:

   * 概要：按日期或有限维度显示简单数据上载
   * 交易 ID：数据上载将在线端点与离线数据连接起来，并将导入的数据与访客在线捕获的快照完全关联（例如，在线完成并离线返回的订单）
   * 完全处理：像处理 Adobe 服务器收集的点击一样处理带有时间戳的数据源。例如，直接将数据插入访客历程。

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)（以前称为 Genesis）**&#x200B;的使用说明：

* 适用于跟已经与 Adobe Analytics 建立受支持连接的第三方提供商合作的情况。Data Connectors 通常会定期将摘要级别的数据自动地永久合并到 Adobe Analytics 中。

**[数据插入 API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)** 的使用说明：

* 适用于需要将数据上载到 Adobe Analytics，但无法使用 Adobe AppMeasurement 或移动 SDK 代码的情况。

**[客户属性](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**&#x200B;的使用说明：

* 适用于您在客户关系管理 (CRM) 数据库中捕获了企业客户数据，并希望将该数据上载到 Experience Cloud 的情况。
* 适用于要在 Analytics 中使用 CRM 数据进行更深入的分析，或要在 Adobe Target 中将该数据作为定位条件的情况。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** 的使用说明：

* 适用于要将诸如人口统计信息（如性别或收入水平）、心理统计信息（如兴趣和爱好）、CRM 数据或广告展示数据之类的 Adobe Audience Manager (AAM) 受众数据合并到任何 Analytics 工作流程中的情况。
* 适用于希望上载的 CRM 数据基于时间（因为此集成会按点击将新信息发送给 Analytics）的情况。

## 从 Adobe Analytics 导出数据 {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)** 的使用说明：

* 适用于工作区的自定义布局选项有限的情况（在 Excel 的限制范围内，Report Builder 可执行任何操作）。
* 用于将用户输入的内容或离线数据源（展示次数、成本）松散绑定到 Adobe 数据。用于将数据关联起来的更为永久的解决方案是数据源（请参阅“将数据导入 Analytics”）。
* 用于将不同维度报表中的数据合并起来（例如，将促销活动展示次数报表和促销活动点击对话报表合并起来）。
* 用于进行跨报表包查看。
* 适用于需要通过计划实现自动化的情况（XLSX、XLSM、CSV、PDF、TXT、XML、MHT）。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** 的使用说明：

* 访问在UI中隐藏的变量- IP地址、Experience Cloud ID、Analytics访问者ID、页面URL)
* 用于访问比 UI 更细粒度的数据（非规范化的表视图）
* 用于下载适用于数据透视表输入格式的数据
* 适用于客户端要将 Adobe 数据输入第三方数据可视化工具的情况（稍微汇总，不是点击级别）
* 用于在 Adobe Analytics 中遇到“低流量”的情况下访问所有独特维度值

**[应使用Analytics数据源](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** ：

* 用于利用 Adobe 可提供的最细粒度的数据馈送（访客 ID、点击量）
* 适用于客户端要在 Adobe 可发送的最细粒度级别发送客户端数据库中存储的 Adobe 数据的情况。
* 适用于客户端要开发商智能 (BI) 工具或将点击级别的 Adobe 数据导入第三方工具的情况.

**[报表 API](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)** 适用于其他可视化选项无法满足您需求的情况。其中包括以下 3 个 API 选项：

* **经过完全处理**：适用于您需要功能丰富的数据（包括访问量、访客量和区段）的情况。这是典型的 Analytics UI 汇总数据，有效期约为 30-90 分钟。可以通过 Report Builder 使用。
* **实时**：适用于要延迟几秒查看若干量度和维度的情况。这是经过部分处理的有限汇总数据，有效期约为 30 秒。其中包含最受欢迎、获胜方和失败方的独特算法。可以通过 Report Builder 使用。
* **[!UICONTROL 实时流]**：适用于要在几秒内收集经过部分处理的点击级别的 Analytics 数据流。这是经过部分处理的数据，有效时间在大约 30 秒之内。仅适用于 Analytics Premium。要求通过某种方式显示数据，通常是通过参与工程技术服务。

## 自定义解决方案 {#section_4A212F26A15947599DFB0399A0440CB6}

应在以下情况使用工程技术服务：:

* 其他 Adobe 工具无法满足您的需求。
* 希望获得自定义体验。
* 希望获得完全自动化的解决方案。
* 希望使用许多设备。
* 拥有多个数据源。
* 您的数据 ETL（提取-转换-加载）要求十分复杂。
* 希望自定义品牌。
* 希望可视化 [!UICONTROL Analytics 实时流]。
