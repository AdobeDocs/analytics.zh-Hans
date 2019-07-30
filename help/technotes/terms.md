---
title: Adobe Analytics中使用的条款
description: Adobe Analytics词汇表，定义常用术语。
translation-type: tm+mt
source-git-commit: 5ca51ad6b967687004d9447964ed87b29077b330

---


# Adobe Analytics中使用的条款

使用此术语表了解Adobe Analytics使用的许多术语的上下文。

* **Admin Console：** 可以引用：
   * 传统管理工具，管理Adobe Analytics中的报告套件设置。在以前版本的Adobe Analytics中，用户权限也在此处管理。See [Admin Tools](../admin/admin/c-admin-tools.md) in the Admin user guide.
   * Adobe管理控制台，可在其中管理产品访问权限并管理用户权限。See [Admin Console](../admin/admin-console/home.md) in the Admin user guide.
* **分配：** 如果在访问期间转换变量遇到多个值，则变量的分配设置决定保留哪个值。See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **异常：** 检测到使用统计建模自动发现数据中意外的趋势。该模型可分析量度并确定值的下限、上限和预期范围。See [Anomaly Detection](../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) in the Analyze user guide.
* **AppMeasurement：** 用于收集数据并将其发送给Adobe的代码库。See the [Homepage](../implement/home.md) of the Implement user guide.
* **ASI空位：** 不再存在。在以前版本的Adobe Analytics中，ASI插槽提供了一个临时报告套件容器来查看分段数据。在Adobe Analytics的当前版本中，可立即将区段应用于任何报告。
* **细分：** 允许您在其他维度的上下文中查看维度。See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **回弹：** 由单次点击组成的访问。See [Bounces](../components/c-variables/c-metrics/metrics-bounces.md) in the Components user guide. 另请参阅单次访问。
* **计算得出的指标：** 允许组合现有指标、统计函数和公式，以便在报表中使用。See [Calculated metrics](../components/c-calcmetrics/cm-overview.md) in the Components user guide.
* **Campaign：** 可以引用：
   * Campaign变量，它填充跟踪代码维度。See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * 跟踪代码维度的默认分类；自动为所有报表包创建。
   * Adobe Campaign，是Adobe Experience Cloud的一部分。More information on [Adobe.com](https://www.adobe.com/marketing/campaign.html).
* **渠道：** 可以引用：
   * “渠道”变量，填充站点区域维度。See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * 营销渠道，这是一个有助于了解用户如何来到您的站点的组件。See [Marketing Channels](../components/c-marketing-channels/c-overview.md) in the Components user guide.
* **分类：** Adobe Analytics中允许维度值分组的功能。See [Classifications](../components/c-classifications2/c-classifications.md) in the Components user guide.
* **点击流数据源：** 请参阅数据源。
* **转换变量：** 称为eVar。存储自定义值，并保留变量值直到它过期。See [Conversion variables](../components/c-variables/dimensionslist/reports-conversion.md) in the Components user guide.
* **相关性：** 不再用作术语；替换为维度划分。在Adobe Analytics的早期版本中，关联授予了分解流量变量的能力。See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **当前数据：** 某些报告中允许包含最近未完全处理的数据的选项。See [Current data](../analyze/reports-analytics/current-data.md) in the Analyze user guide.
* **自定义链接：** 包含非页面查看数据的点击类型。See the [s.tl() function](../implement/js-implementation/function-tl.md) in the Implement user guide. 另请参阅点击。
* **客户属性：** Experience Cloud功能，可上传属性数据。See [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the Core Services user guide.
* **客户支持代表：** 有权直接与Adobe客户服务部门交互的指定用户。See [Customer support delegates](https://helpx.adobe.com/experience-cloud/supported-users.html) in the Experience Cloud Knowledgebase.
* **数据连接器：** 一个完整的开发解决方案，它允许第三方自动将数据上传至Adobe Analytics。该第三方的客户可以使用数据连接器在Adobe Analytics中丰富其数据。大多数数据连接器使用在数据源中使用的类似工作流。请参阅导入用户指南中的数据连接器。
* **数据源：** 一个原始数据导出，它将每个点击作为一行列出，并将变量列出为单独的列。最常用于将Adobe Analytics数据导出到第三方数据库。See [Data feeds](../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.
* **数据源：** 允许用户将文件中的数据上载到Adobe Analytics。该文件通常从FTP站点中提取。See [Data Sources](../import/c-data-sources/datasrc-home.md) in the Import user guide.
* **数据仓库：** Adobe Analytics中允许您请求更大报表的功能。See [Data Warehouse](../export/data-warehouse/data-warehouse.md) in the Export user guide.
* **Dimension：** 包含可变值(如文本)的组件类型。示例包括页面名称、跟踪代码或引用域。指标通常是其对应的指标。
* **动态标签管理：** Adobe以前的标签管理解决方案。See [DTM implementation overview](../implement/c-implement-with-dtm/dtm-implementation-overview.md) in the Implement user guide. Adobe建议改用Adobe Experience Platform Launch。
* **事件序列化：** 实施措施的过程可防止重复事件收集。See [Event serialization](../implement/js-implementation/event-serialization.md) in the Implement user guide.
* **eVar：** 请参阅转换变量。
* **事件：** 请参阅成功事件。
* **ExcelClient：** 不再用作术语。Report Builder的前身名称。
* **到期：** 在转换变量的上下文中，该值在后端保留的持续时间。此持久性允许事件在事件点击之前与变量值相关联。See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **流：** Analysis Workspace中的一种可视化类型，它显示用户在站点中采取的路径。See [Flow visualization](../analyze/analysis-workspace/visualizations/c-flow/flow.md) in the Analyze user guide.
* **Genesis：** 不再用作术语。以前的数据连接器名称。
* **全局报告套件：** 指定到报告套件的非正式术语，用于收集来自多个站点的点击量。
* **H代码：** AppMeasurement的前身。在旧版本的Adobe Analytics中，代码版本由“H版本”(如H24、H23.1等)测量。
* **点击：** 发送到Adobe数据收集服务器的单个图像请求。页面视图和自定义链接均可被称为点击。
* **图像请求：** 用于与Adobe数据收集服务器进行通信的透明1x像素图像。网站使用包含数据的长查询字符串请求此不可见的图像；Adobe返回不可见的图像并解析收到的查询字符串。
* **Insight：** 可以引用：
   * Data Workbench的前名。
   * 自定义分析，自定义流量变量的历史名称。
* **KPI：** 用于关键绩效指标的缩写。帮助企业了解其网站表现的指标。每个组织都有不同的KPI，可衡量其业务的不同方面。See [Create a solution design document](../implement/prepare/solution-design.md) in the Implement user guide.
* **延迟：** 收集数据和报告中的可用时间之间的延迟。报告套件中的典型滞后时间为30-90分钟。See [Latency](../technotes/latency.md) in the Technotes user guide.
* **启动项：** Adobe Experience Platform Launch，Adobe最新实施解决方案。See [Overview](https://docs.adobe.com/content/help/en/launch/using/overview.html) in the Adobe Experience Platform Launch user guide.
* **列表prop：** 可转换典型流量变量以支持同一点击中多个值的设置。如果启用此设置，任何自定义流量变量都可以成为列表prop。See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **列表变量：** 不同于转化变量的不同变量。列表变量支持同一点击中的多个值，而变量值会在访问中保留，类似于转化变量。组织只有三个列表变量。See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **登录公司：** 单位使用的报表包集合。一些组织有多个适用于其组织不同部分的登录公司。
* **指标：** 包含定量数据的组件类型。量度值通常包含数字，例如页面视图、访问和收入。维度通常是其对应的维度。
* **多包标记：** 向多个报表包发送相同点击的做法。通过虚拟报告套件的介绍，基本上不再需要这种做法。大多数多包标记工作有助于适应全局报告套件。
* **标准化：** 一种组织所有指标并将其强制加入比例的可视化方式，允许更轻松地对比趋势。
* **Omniture：** 不再用作术语。在2009年被Adobe收购之前，拥有Adobe Analytics的组织。
* **路径：** 请参阅流量。
* **排名报告：** 通常跟在维度后面的报表格式。此类型的报告允许您查看热门项目，如站点上查看最多的页面。另请参阅趋势报告。
* **实时：** 在收集所配置的变量后立即显示它们，并且不会延迟。See [Real-time reports](../admin/admin/realtime/realtime.md) in the Admin user guide.
* **报表套件：** 将数据发送到的覆盖容器。Adobe Analytics中的所有报告均引用一个报告套件。
* **RSID：** 报告套件ID的缩写。报表包具有友好名称和报表包ID。
* **页面视图：** 增加页面视图的点击类型。See [Page views](../components/c-variables/c-metrics/metrics-page-view.md) in the Components user guide. 另请参阅点击。
* **处理规则：** 可以引用：
   * 处理规则，一种使用管理控制台中的特定规则更改数据收集的方法。See [Processing rules](../admin/admin/c-processing-rules/processing-rules.md) in the Admin user guide.
   * 营销渠道处理规则，一组规则，用于确定点击属于哪个营销渠道。See [Marketing channel processing rules](../admin/admin/marketing-channels-admin.md) in the Admin user guide.
* **Prop：** 请参阅流量变量。
* **s. t()：** AppMeasurement库中用于发送页面查看图像请求的函数名称。Some AppMeasurement libraries use `s.track()` instead. See [s.t()](../implement/js-implementation/function-t.md) in the Implement user guide.
* **<span>s.</span>tl()：** 用于发送链接跟踪图像请求的AppMeasurement库中函数的名称。Some AppMeasurement libraries use `s.trackLink()` instead. See [s.tl()](../implement/js-implementation/function-tl.md) in the Implement user guide.
* **卫星：** 不再用作术语。Dynamic Tag Management的前一产品名称。
* **区段：** 允许您专注于数据的特定子集。See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **区段容器：** 区段的部分，用于确定要引入的数据。容器可基于页面查看、访问或访客。See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **序列化：** 请参阅活动序列化。
* **服务器调用：** 图像请求或点击的替代名称，主要用于计费上下文。
* **单次访问：** 一个访问，其中维度只有唯一的唯一值。访问可能有多个点击，只要没有多个唯一值。See [Single access](../components/c-variables/c-metrics/metrics-single-access.md) in the Components user guide. 另请参阅回弹。
* **SiteCatalyst：** 不再用作术语。Adobe Analytics的先前产品名称。
* **子关系：** 不再用作术语；替换为维度划分。在以前版本的Adobe Analytics中，子关系授予了划分转化变量的能力。See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **成功事件：** 用户采取的跟踪操作。您的单位决定要跟踪的事件以及用于跟踪其的成功事件变量。See [Custom events](../components/c-variables/c-metrics/metrics-custom.md) in the Components user guide.
* **支持的用户：** 请参阅客户支持代表。
* **流量变量：** 通常称为props。为单次点击存储自定义值。早期版本的Adobe Analytics为prop提供了独特的价值，但对平台的改进使得自定义流量变量很大程度上不必要。在大多数情况下，Adobe建议使用自定义转化变量(eVar)。See [Custom traffic variables](../components/c-variables/dimensionslist/reports-custom-traffic.md) in the Components user guide.
* **趋势报告：** 通常向量度显示多个日期范围的报告格式。此类型的报告允许您查看某个指标随着时间的推移方式。另请参阅排名报告。
* **唯一访客**：表示访问您的站点的唯一个人的数量。单个独特访客可以多次访问。See [Unique visitor](../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide.
* **虚拟报告套件：** 引用常规报表包并允许优化数据的数据的虚拟容器。数据不会发送到虚拟报告套件；而是会将数据发送到常规报告套件，而虚拟报告套件则会构建在收集到的数据之外。See [Virtual report suites](../components/vrs/vrs-about.md) in the Components user guide.
* **访问：** 表示在您的站点上进行的唯一会话数。See [Visits](../components/c-variables/c-metrics/metrics-visit.md) in the Components user guide.
* **VISTA规则：** 由Adobe根据客户要求复制、分析或过滤数据服务器端的自定义逻辑。VISTA规则通常会产生额外的成本。另请参阅处理规则。
* **网络信标：** 请参阅图像请求。
