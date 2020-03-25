---
description: 此帮助页面包含每个Adobe Analytics工具的推荐用例。 工具的列出顺序应考虑在内。 如果某个工具不满足需求，请移到下一个工具进行考虑。
title: 我应该使用哪种 Adobe Analytics 工具？
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: f7125e6845a653ca3d4dd3f1313d1b39f564459c

---


# 我应该使用哪种 Adobe Analytics 工具？

此帮助页面包含每个Adobe Analytics工具的推荐用例。 工具的列出顺序应考虑在内。 如果某个工具不满足需求，请移到下一个工具进行考虑。

有关Adobe Analytics产品比较的更多信息，请访 [问此处](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md)。

## Adobe Analytics 报表用户界面 {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)**应该是您的首选用户界面，可满足您所有的报告与分析需求。Adobe 会继续投入人力和物力坚持每月发布此产品的更新。如果有任务无法在 Analysis Workspace 中完成，您可以考虑使用下面列出的其他界面。**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**的使用说明：

* 适用于需要访问更易导航的预构建报表的初学用户。
* 了解目标活动(Analytics for目标/A4T)提升和信心。
* 在UI中访问实时数据。
* 设置日历事件。
* 设置目标。
* 敬视图机器人报告。
* 要访问并发查看器、视频时段和查看器下拉的唯一视频可视化，请执行以下操作：
* 在计划报告中利用发布列表。

**[Mobile Services UI](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)**的使用说明：

* 如果需要孤立的视图移动应用程序数据。
* 管理移动应用程序SDK的实施。
* 设置移动广告，如应用程序内消息传递、推送消息和位置定位。
* 如果需要更多交互式可视化来查看应用程序数据(Sunburst)。
* 在地图上可视化感兴趣的点。
* 对于“生命周期”价值指标。

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**的使用说明：

* 导出50,000行数据
* 如果需要项目工作的选项卡组织。
* 使用网站分析报表（3D路径报表）。

**[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**的使用说明：

* 作为最灵活的Analytics工具选项(下至访客级、点击级分析)。
* 创建从CRM到POS再到Web的线上和线下互动的多渠道数据集。
* 适用于高级归因（基于规则和算法模型）。
* 用于预测、统计建模（倾向评分、聚类、关联等）。
* 对于延迟分析(事件之前／之后的时间)。
* 用于识别和导出整个Adobe Experience Cloud中的复杂细分。

## 将数据导入Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[分类](/help/components/c-classifications2/c-classifications.md)**的使用说明：

* 当存在要与收集值(eVar、prop、营销渠道)关联的元数据时
* 选项:

   * 规则构建器：当您为变量（如分隔值）收集了可预测的格式化值时使用。 这种方法允许您建立规则，基本上是“设定并忘记”。
   * 浏览器导入器：可在没有可预测的值或需要一次性更新有限的值列表时使用。此方法要求您持续监控分类的新值。

**[数据源](/help/import/c-data-sources/datasrc-home.md)**的使用说明：

* 适用于要将离线数据永久写入 Adobe Analytics 的情况
* 选项:

   * 摘要：简单的数据上传，按日或有限维度
   * 交易ID:将联机端点连接到脱机数据并将导入的数据完全关联到联机捕获的访客快照（例如，在线完成订单和脱机返回订单）的数据上传
   * 完全处理：加盖时间戳的数据源，处理方式就像是Adobe服务器收集的点击一样。 即数据直接插入访客旅程。

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)（以前称为 Genesis）**的使用说明：

* 当您与已使用Adobe Analytics构建受支持连接的第三方提供商接洽时。 Data Connectors通常会定期将摘要级别数据永久自动地并入Adobe Analytics中。

**[数据插入 API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**的使用说明：

* 适用于需要将数据上载到 Adobe Analytics，但无法使用 Adobe AppMeasurement 或移动 SDK 代码的情况。

**[客户属性](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**的使用说明：

* 如果您在客户关系管理(CRM)数据库中捕获企业客户数据，并希望将数据上传到Experience Cloud。
* 如果您希望在Analytics中使用CRM数据进行更深入的分析，或在Adobe目标中将其用作定位标准。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**的使用说明：

* 如果要将Adobe受众管理器(AAM)受众数据(如人口统计信息（如性别或收入水平）、心理信息（如兴趣和爱好）、CRM数据或广告印象数据)合并到任何Analytics工作流程中。
* 如果您希望上传的CRM数据基于时间，因为此集成会将新信息发送到点击后的Analytics。

## 从Adobe Analytics导出数据 {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)**的使用说明：

* 如果Workspace的自定义布局选项有限（Report Builder中的任何功能均可在Excel的限制内实现）。
* 松散地将用户输入或离线数据源（印象、成本）与Adobe数据绑定。 用于绑定数据的更永久解决方案是数据源（请参阅将数据导入分析）。
* 要将不同维度报表的数据合并在一起（例如，与促销点击转化报表一起加入的促销印象报表）。
* 用于跨报表包视图。
* 如果需要通过计划实现自动化(XLSX、XLSM、CSV、PDF、TXT、XML、MHT)。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**的使用说明：

* 用于访问隐藏在 UI 中的变量，包括 IP 地址、Experience Cloud ID、Analytics 访客 ID、页面 URL
* 要访问比UI更精细的数据(非规范化表视图)
* 以适用于透视表输入的格式下载数据
* 如果客户希望将Adobe数据输入到第三方数据可视化工具中（稍微总结一下，而非点击级别）
* 用于在 Adobe Analytics 中遇到“低流量”的情况下访问所有独特维度值

应使用 **[Analytics 数据馈送](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**：

* 为了利用我们可以提供的最精细的数据馈送(访客ID、点击)。
* 如果客户端希望将Adobe数据存储在客户端数据库中，则可以发送最精细的数据。
* 如果客户希望开发Business Intelligence(BI)工具或将点击级Adobe数据输入到第三方工具中。

**[报表 API](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**适用于其他可视化选项无法满足您需求的情况。3个API选项包括：

* **完全处理**:当您需要功能丰富的数据(包括访问、访客和细分)时。 这是典型的Analytics UI汇总数据，在约30-90分钟内可用。 可通过Report Builder使用。
* **实时**:当您希望将一些度量和维度视图并等待数秒的延迟时。 这是有限的、部分处理的、汇总的数据，在约30秒内可用。 包括最受欢迎的、获胜方和失败方的独特算法。 可通过Report Builder使用。
* **[!UICONTROL Live Stream]**:当您希望在收集后的数秒内获得经过部分处理的命中级分析数据流时。 这是部分处理的数据，在约30秒内可用。 仅适用于Analytics Premium。 需要某种方式来可视化数据，通常通过工程服务参与。

## 自定义解决方案 {#section_4A212F26A15947599DFB0399A0440CB6}

应在以下情况使用工程技术服务：

* 其他 Adobe 工具无法满足您的需求。
* 您需要自定义体验。
* 您需要一款完全自动化的解决方案。
* 您希望访问许多设备。
* 您有多个数据源。
* 您有复杂的数据ETL（提取——转换——加载）要求。
* 您需要自定义品牌。
* 您希望可视化 [!UICONTROL Analytics Live Stream]。
