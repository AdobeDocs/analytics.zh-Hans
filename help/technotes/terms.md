---
title: Adobe Analytics中使用的条款
description: Adobe Analytics词汇表，定义常用术语。
translation-type: tm+mt
source-git-commit: aeb2fc9f53aec6b4e53378b87e64c01f0b437d87

---


# Adobe Analytics中使用的条款

使用此术语表了解Adobe Analytics使用的许多术语的上下文。

* **活动地图：** 一个浏览器插件，它显示了站点上的哪些区域被点击最多。请参阅 [分析用户指南中的活动地图](../analyze/activity-map/activity-map.md) 。
* **Admin Console：** 可以引用：
   * 传统管理工具，管理Adobe Analytics中的报告套件设置。在以前版本的Adobe Analytics中，用户权限也在此处管理。请参阅管理员用户指南中的 [管理员工具](../admin/admin/c-admin-tools.md) 。
   * Adobe管理控制台，可在其中管理产品访问权限并管理用户权限。请参阅管理员用户指南中的 [Admin Console](../admin/admin-console/home.md) 。
* **分配：** 如果在访问期间转换变量遇到多个值，则变量的分配设置决定保留哪个值。See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **异常：** 检测到使用统计建模自动发现数据中意外的趋势。该模型可分析量度并确定值的下限、上限和预期范围。请参阅 [分析用户指南中的异常检测](../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) 。
* **AppMeasurement：** 用于收集数据并将其发送给Adobe的代码库。请参阅实施用户指南 [主页](../implement/home.md) 。
* **ASI空位：** 不再存在。在以前版本的Adobe Analytics中，ASI插槽提供了一个临时报告套件容器来查看分段数据。在Adobe Analytics的当前版本中，可立即将区段应用于任何报告。
* **细分：** 允许您在其他维度的上下文中查看维度。请参阅 [分析用户指南中的分解维度](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) 。
* **回弹：** 由单次点击组成的访问。请 [参阅组件用户指南中的弹回。](../components/c-variables/c-metrics/metrics-bounces.md)另请参阅单次访问。
* **计算得出的指标：** 允许组合现有指标、统计函数和公式，以便在报表中使用。请参阅 [组件用户指南中的计算量度](../components/c-calcmetrics/cm-overview.md) 。
* **Campaign：** 可以引用：
   * Campaign变量，它填充跟踪代码维度。请参阅 [实施用户指南](../implement/js-implementation/c-variables/page-variables.md) 中的页面变量。
   * 跟踪代码维度的默认分类；自动为所有报表包创建。
   * Adobe Campaign，是Adobe Experience Cloud的一部分。有关 [Adobe.com](https://www.adobe.com/marketing/campaign.html)的更多信息。
* **渠道：** 可以引用：
   * “渠道”变量，填充站点区域维度。请参阅 [实施用户指南](../implement/js-implementation/c-variables/page-variables.md) 中的页面变量。
   * 营销渠道，这是一个有助于了解用户如何来到您的站点的组件。请参阅组件用户指南中的 [营销渠道](../components/c-marketing-channels/c-overview.md) 。
* **分类：** Adobe Analytics中允许维度值分组的功能。请参阅 [组件用户指南中的分类](../components/c-classifications2/c-classifications.md) 。
* **Clickmap：** 不再使用。一个旧版浏览器插件，它显示了站点上的哪些区域被点击最多。此工具已停用，有利于活动地图。
* **点击流数据源：** 请参阅数据源。
* **Cohount：** 一组在特定时间段内共享共同特征的人员。See [What is Cohort Analysis?](../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) 分析用户指南中。
* **集合服务器：** 请参阅数据收集服务器。
* **转换变量：** 称为eVar。存储自定义值，并保留变量值直到它过期。See [Conversion variables](../components/c-variables/dimensionslist/reports-conversion.md) in the Components user guide.
* **相关性：** 不再用作术语；替换为维度划分。在Adobe Analytics的早期版本中，关联授予了分解流量变量的能力。请参阅 [分析用户指南中的分解维度](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) 。
* **当前数据：** 某些报告中允许包含最近未完全处理的数据的选项。请参阅 [分析用户指南中的当前数据](../analyze/reports-analytics/current-data.md) 。
* **自定义链接：** 包含非页面查看数据的点击类型。请参阅“实施用户指南”中的 [s. tl()函数](../implement/js-implementation/function-tl.md) 。另请参阅点击。
* **客户属性：** Experience Cloud功能，可上传属性数据。请参阅 [核心服务用户指南中的客户属性](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) 。
* **客户支持代表：** 有权直接与Adobe客户服务部门交互的指定用户。请参阅 [Experience Cloud知识库](https://helpx.adobe.com/experience-cloud/supported-users.html) 中的客户支持代表。
* **数据收集服务器：** 接收和处理数据的Adobe自有服务器。图像请求发送到Adobe的数据收集服务器以用于报告。
* **数据连接器：** 一个完整的开发解决方案，它允许第三方自动将数据上传至Adobe Analytics。该第三方的客户可以使用数据连接器在Adobe Analytics中丰富其数据。大多数数据连接器使用在数据源中使用的类似工作流。请参阅导入用户指南中的数据连接器。
* **数据源：** 一个原始数据导出，它将每个点击作为一行列出，并将变量列出为单独的列。最常用于将Adobe Analytics数据导出到第三方数据库。请参阅 [导出用户指南中的数据源](../export/analytics-data-feed/c-getstarted/data-feed-overview.md) 。
* **数据源：** 允许用户将文件中的数据上载到Adobe Analytics。该文件通常从FTP站点中提取。请参阅 [导入用户指南中的数据源](../import/c-data-sources/datasrc-home.md) 。
* **数据仓库：** Adobe Analytics中允许您请求更大报表的功能。请参阅 [导出用户指南中的数据仓库](../export/data-warehouse/data-warehouse.md) 。
* **Dimension：** 包含可变值(如文本)的组件类型。示例包括页面名称、跟踪代码或引用域。指标通常是其对应的指标。
* **动态标签管理：** Adobe以前的标签管理解决方案。请参阅 [“实施用户指南”](../implement/c-implement-with-dtm/dtm-implementation-overview.md) 中的DTM实施概述。Adobe建议改用Adobe Experience Platform Launch。
* **事件序列化：** 实施措施的过程可防止重复事件收集。请参阅 [“实施用户指南”](../implement/js-implementation/event-serialization.md) 中的活动序列化。
* **eVar：** 请参阅转换变量。
* **事件：** 请参阅成功事件。
* **ExcelClient：** 不再用作术语。Report Builder的前身名称。
* **到期：** 在转换变量的上下文中，该值在后端保留的持续时间。此持久性允许事件在事件点击之前与变量值相关联。See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **流：** Analysis Workspace中的一种可视化类型，它显示用户在站点中采取的路径。请参阅 [分析用户指南中的流量可视化](../analyze/analysis-workspace/visualizations/c-flow/flow.md) 。
* **Genesis：** 不再用作术语。以前的数据连接器名称。
* **全局报告套件：** 指定到报告套件的非正式术语，用于收集来自多个站点的点击量。
* **H代码：** AppMeasurement的前身。在旧版本的Adobe Analytics中，代码版本由“H版本”测量，如H.27.5、H.26等。
* **点击：** 发送到Adobe数据收集服务器的单个图像请求。页面视图和自定义链接均可被称为点击。
* **图像请求：** 用于与Adobe数据收集服务器进行通信的透明1x像素图像。网站使用包含数据的长查询字符串请求此不可见的图像；Adobe返回不可见的图像并解析收到的查询字符串。
* **Insight：** 可以引用：
   * Data Workbench的前名。
   * 自定义分析，自定义流量变量的历史名称。
* **KPI：** 用于关键绩效指标的缩写。帮助企业了解其网站表现的指标。每个组织都有不同的KPI，可衡量其业务的不同方面。请参阅 [“实施用户指南”中的创建解决方案设计文档](../implement/prepare/solution-design.md) 。
* **延迟：** 收集数据和报告中的可用时间之间的延迟。报告套件中的典型滞后时间为30-90分钟。请参阅 [TechNotes用户指南中](../technotes/latency.md) 的延迟。
* **启动项：** Adobe Experience Platform Launch，Adobe最新实施解决方案。请参阅 [Adobe](https://docs.adobe.com/content/help/en/launch/using/overview.html) Experience Platform Launch用户指南中的概述。
* **列表prop：** 可转换典型流量变量以支持同一点击中多个值的设置。如果启用此设置，任何自定义流量变量都可以成为列表prop。请参阅 [实施用户指南](../implement/js-implementation/c-variables/page-variables.md) 中的页面变量。
* **列表变量：** 不同于转化变量的不同变量。列表变量支持同一点击中的多个值，而变量值会在访问中保留，类似于转化变量。组织只有三个列表变量。请参阅 [实施用户指南](../implement/js-implementation/c-variables/page-variables.md) 中的页面变量。
* **登录公司：** 单位使用的报表包集合。一些组织有多个适用于其组织不同部分的登录公司。
* **营销渠道：** Adobe Analytics中的一项功能，可根据客户如何到达您的网站进行分类。可使用营销渠道处理规则自定义用于分类点击的逻辑。请参阅 [组件用户指南中的营销渠道](../components/c-marketing-channels/c-getting-started-mchannel.md) 快速入门。
* **指标：** 包含定量数据的组件类型。量度值通常包含数字，例如页面视图、访问和收入。维度通常是其对应的维度。
* **多包标记：** 向多个报表包发送相同点击的做法。通过虚拟报告套件的介绍，基本上不再需要这种做法。大多数多包标记工作有助于适应全局报告套件。
* **标准化：** 一种组织所有指标并将其强制加入比例的可视化方式，允许更轻松地对比趋势。
* **发生次数：** 一种指标类型，用于显示设置或持续的点击尺寸值。请参阅 [组件用户指南中的出现](../components/c-variables/c-metrics/metrics-occurrences.md) 。
* **Omniture：** 不再用作术语。在2009年被Adobe收购之前，拥有Adobe Analytics的组织。
* **路径：** 请参阅流量。
* **页面视图：** 增加页面视图的点击类型。请参阅 [组件用户指南](../components/c-variables/c-metrics/metrics-page-view.md) 中的页面视图。另请参阅点击。
* **持久性：** 转化变量的抽象概念，允许在不同点击发生的变量值和事件之间建立链接。另请参阅过期。
* **主服务器调用：** 图像请求或点击的替代名称，主要用于多包标记和计费上下文。将同一点击发送到多个报表包时，第一个报表包是主服务器调用，而其余则是次要服务器调用。此规则适用于所有点击类型，包括页面查看和链接跟踪。另请参阅辅助服务器调用。
* **处理规则：** 可以引用：
   * 处理规则，一种使用管理控制台中的特定规则更改数据收集的方法。See [Processing rules](../admin/admin/c-processing-rules/processing-rules.md) in the Admin user guide.
   * 营销渠道处理规则，一组规则，用于确定点击属于哪个营销渠道。请参阅 [管理用户指南中的营销渠道处理规则](../admin/admin/marketing-channels-admin.md) 。
* **Prop：** 请参阅流量变量。
* **排名报告：** 通常跟在维度后面的报表格式。此类型的报告允许您查看热门项目，如站点上查看最多的页面。另请参阅趋势报告。
* **实时：** 在收集所配置的变量后立即显示它们，并且不会延迟。请参阅管理用户指南中的 [实时报告](../admin/admin/realtime/realtime.md) 。
* **报表套件：** 将数据发送到的覆盖容器。Adobe Analytics中的所有报告均引用一个报告套件。
* **滚动日期范围：** 随时间推移变化的相对日期范围类型。例如，显示过去天的报告可视为滚动日期范围。另请参阅静态日期范围。
* **RSID：** 报告套件ID的缩写。报表包具有友好名称和报表包ID。
* **s. t()：** AppMeasurement库中用于发送页面查看图像请求的函数名称。而是使用一些AppMeasurement `s.track()` 库。请参阅 [“实施用户指南”中的s. t()](../implement/js-implementation/function-t.md) 。
* **<span>s.</span>tl()：** 用于发送链接跟踪图像请求的AppMeasurement库中函数的名称。而是使用一些AppMeasurement `s.trackLink()` 库。请参阅 [“实施用户指南”](../implement/js-implementation/function-tl.md) 中的s. tl()。
* **s_ code. js：** 在Adobe Analytics的历史版本中使用的JavaScript文件的名称。使用的JavaScript文件的当前名称为AppMeasurement. js。
* **卫星：** 不再用作术语。Dynamic Tag Management的前一产品名称。
* **辅助服务器调用：** 图像请求或点击的替代名称，主要用于多包标记和计费上下文。当同一点击发送到多个报表包时，第一个列出的所有报表包都是次要服务器调用。另请参阅主服务器调用。
* **区段：** 允许您专注于数据的特定子集。请参阅 [组件用户指南中](../components/c-segmentation/seg-overview.md) 的分段。
* **区段容器：** 区段的部分，用于确定要引入的数据。容器可基于页面查看、访问或访客。请参阅 [组件用户指南中](../components/c-segmentation/seg-overview.md) 的分段。
* **序列化：** 请参阅活动序列化。
* **服务器调用：** 图像请求或点击的替代名称，主要用于计费上下文。
* **单次访问：** 一个访问，其中维度只有唯一的唯一值。访问可能有多个点击，只要没有多个唯一值。请参阅 [组件用户指南](../components/c-variables/c-metrics/metrics-single-access.md) 中的单次访问。另请参阅回弹。
* **SiteCatalyst：** 不再用作术语。Adobe Analytics的先前产品名称。
* **子关系：** 不再用作术语；替换为维度划分。在以前版本的Adobe Analytics中，子关系授予了划分转化变量的能力。请参阅 [分析用户指南中的分解维度](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) 。
* **成功事件：** 用户采取的跟踪操作。您的单位决定要跟踪的事件以及用于跟踪其的成功事件变量。请参阅 [组件用户指南](../components/c-variables/c-metrics/metrics-custom.md) 中的自定义事件。
* **支持的用户：** 请参阅客户支持代表。
* **流量变量：** 通常称为props。为单次点击存储自定义值。早期版本的Adobe Analytics为prop提供了独特的价值，但对平台的改进使得自定义流量变量很大程度上不必要。在大多数情况下，Adobe建议使用自定义转化变量(eVar)。请参阅 [组件用户指南中的自定义流量变量](../components/c-variables/dimensionslist/reports-custom-traffic.md) 。
* **趋势报告：** 通常向量度显示多个日期范围的报告格式。此类型的报告允许您查看某个指标随着时间的推移方式。另请参阅排名报告。
* **唯一访客**：表示访问您的站点的唯一个人的数量。单个独特访客可以多次访问。请参阅 [组件用户指南中的唯一访客](../components/c-variables/c-metrics/metrics-unique-visitors.md) 。
* **虚拟报告套件：** 引用常规报表包并允许优化数据的数据的虚拟容器。数据不会发送到虚拟报告套件；而是会将数据发送到常规报告套件，而虚拟报告套件则会构建在收集到的数据之外。请参阅 [组件用户指南中的虚拟报告套件](../components/vrs/vrs-about.md) 。
* **访问：** 表示在您的站点上进行的唯一会话数。请参阅 [组件用户指南中](../components/c-variables/c-metrics/metrics-visit.md) 的访问。
* **VISTA规则：** 由Adobe根据客户要求复制、分析或过滤数据服务器端的自定义逻辑。VISTA规则通常会产生额外的成本。另请参阅处理规则。
* **网络信标：** 请参阅图像请求。
