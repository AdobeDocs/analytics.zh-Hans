---
title: Adobe Analytics 中使用的术语
description: Adobe Analytics 词汇表，用于定义常用术语。
exl-id: 07507ba1-a512-48d9-8022-6084de4ae262
feature: Implementation Basics
source-git-commit: 3eb140c729d2c0e9f880a6fada8377639f7c4a9c
workflow-type: tm+mt
source-wordcount: '2580'
ht-degree: 89%

---

# Adobe Analytics 中使用的术语

使用此术语表可了解 Adobe Analytics 使用的许多术语的上下文。

* **Activity map：**&#x200B;一个浏览器插件，用于显示您网站上哪些区域的点击率最高。请参阅分析用户指南中的 [Activity Map](/help/analyze/activity-map/overview.md)。
* **Admin Console：**&#x200B;可以称为：
   * 旧版管理工具，用于管理 Adobe Analytics 中的报表包设置。在 Adobe Analytics 的先前版本中，用户权限也是在这里进行管理。请参阅管理用户指南中的[管理工具](/help/admin/admin/c-admin-tools.md)。
   * Adobe Admin Console，可用于配置产品访问权限和管理用户权限。请参阅管理用户指南中的 [Admin Console](/help/admin/admin-console/home.md)。
* **分配：**&#x200B;如果转化变量在访问期间遇到多个值，则该变量的分配设置将决定保留哪个值。请参阅管理用户指南中的[转化变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。
* **Analysis Workspace：**&#x200B;用于构建强大的自定义分析项目和实现分析民主化的浏览器解决方案。请参阅《Analysis Workspace工具指南》中的[Analytics概述](/help/analyze/analysis-workspace/home.md)。
* **异常：**&#x200B;通过使用统计建模自动查找数据中的意外趋势，可检测异常。该模型可分析量度并确定值的下限、上限和预期范围。请参阅“Analytics工具指南”中的[异常检测](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)。
* **AppMeasurement：**&#x200B;用于收集数据并将其发送到 Adobe 的代码库。请参阅《实施用户指南》中的[主页](/help/implement/home.md)。
* **ASI 插槽：**&#x200B;不再存在。在 Adobe Analytics 的先前版本中，ASI 插槽提供了一个用于查看分段数据的临时报表包容器。在 Adobe Analytics 的当前版本中，区段可立即应用于任何报表。
* **划分：**&#x200B;允许您在另一个维度的上下文中查看维度。请参阅“Analytics工具指南”中的[划分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。
* **跳出：**&#x200B;包含一次点击的访问。请参阅《组件用户指南》中的[跳出](/help/components/metrics/bounces.md)。另请参阅“单次存取”。
* **计算量度：**&#x200B;允许将现有量度、统计函数和公式的组合用于报告。请参阅《组件用户指南》中的[计算量度](/help/components/c-calcmetrics/cm-overview.md)。
* **促销活动：**&#x200B;可以称为：
   * 促销活动变量，用于填充“跟踪代码”维度。请参阅《实施用户指南》中的[促销活动](../implement/vars/page-vars/campaign.md)。
   * 跟踪代码维度的默认分类；将自动为所有报表包创建。
   * Adobe Campaign 是 Adobe Experience Cloud 的一部分。可在 [Adobe.com](https://www.adobe.com/cn/marketing/campaign.html) 查看更多相关信息。
* **渠道：**&#x200B;可以称为：
   * 渠道变量，用于填充“网站区域”维度。请参阅《实施用户指南》中的[页面变量](/help/implement/vars/page-vars/page-variables.md)。
   * 营销渠道，可以帮助了解用户如何到达您网站的组件。请参阅《组件用户指南》中的[营销渠道](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。
* **分类：** Adobe Analytics 中允许对维度项目进行分组的功能。请参阅《组件用户指南》中的[分类](/help/components/classifications/c-classifications.md)。
* **Clickmap：**&#x200B;不再使用。一个旧版浏览器插件，用于显示您网站上哪些区域的点击率最高。此工具已停用，改为Activity Map。
* **点击流数据馈送：**&#x200B;请参阅“数据馈送”。
* **同类群组：**&#x200B;一组在特定时间段内具有共同特征的人员。请参阅分析用户指南中的[什么是队列分析？Analytics工具指南中的](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)。
* **收集服务器：**&#x200B;请参阅“数据收集服务器”。
* **组件：** Analysis Workspace中的组件包括维度、量度、区段、日期范围、警报和计算量度，您可以将这些组件拖放到项目中。 请参阅《Analytics工具指南》中的[组件概述](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。
* **上下文数据变量：**&#x200B;仅用于处理规则的临时变量。如果处理规则未将上下文数据变量值复制到转化或流量变量，则上下文数据变量值将永久丢失。请参阅《实施用户指南》中的[上下文数据变量](../implement/vars/page-vars/contextdata.md)。
* **转化变量：**&#x200B;也称为 eVar。存储自定义值，并保留变量值，直到其过期。请参阅《组件用户指南》中的 [eVar](/help/components/dimensions/evar.md) 维度。
* **关联：**&#x200B;不再用作术语；替换为维度划分。在 Adobe Analytics 的早期版本中，通过关联可以划分流量变量。请参阅“Analytics工具指南”中的[划分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。
* **自定义链接：**&#x200B;包含非页面视图数据的点击类型。请参阅《实施用户指南》中的 [s.tl() 函数](../implement/vars/functions/tl-method.md)。另请参阅“点击”。
* **客户属性：** Experience Cloud 的一项功能，允许上载属性数据。请参阅《核心服务用户指南》中的[客户属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hans)。
* **数据收集服务器：**&#x200B;接收和处理数据的 Adobe 自有服务器。图像请求将发送到 Adobe 的数据收集服务器以用于报告。
* **Data Connectors：**&#x200B;已停用的开发解决方案，允许第三方自动将数据上载到Adobe Analytics。 该第三方的客户可以使用数据连接器在 Adobe Analytics 中丰富其数据。已替换为[Adobe Exchange市场](https://exchange.adobe.com/apps/browse/ec?product=ANLYTC&amp;partnerLevel=All&amp;sort=RELEVANCE)。
* **数据馈送：**&#x200B;将每次点击列为行，将变量列为单独的列的原始数据导出。最常用于将 Adobe Analytics 数据导出到第三方数据库。请参阅《导出用户指南》中的[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)。
* **数据层：** [数据层](/help/implement/prepare/data-layer.md)是网站上JavaScript对象的框架，其中包含Analytics实施中使用的变量值。 在为 Analytics 变量分配值时，它可以帮助更好地控制和更轻松地维护变量值。
* **数据源：**&#x200B;允许用户将数据从文件上载到 Adobe Analytics。文件通常从 FTP 站点中提取。请参阅《导入用户指南》中的[数据源](/help/import/data-sources/overview.md)。
* **Data Warehouse：** Adobe Analytics 中的一项功能，允许您请求更大的报表。请参阅《导出用户指南》中的 [Data Warehouse](/help/export/data-warehouse/data-warehouse.md)。
* **Data Workbench：** [已停用](https://experienceleague.adobe.com/zh-hans/docs/discontinued/using/data-workbench)分析工具，用于收集、处理、分析和可视化来自多个渠道间在线和离线客户交互的数据。
* **Dimension：**&#x200B;维度是非数字值和日期，如性别、月份、年龄、忠诚度、监视器分辨率等。 其他示例包括页面名称、跟踪代码或反向链接域名。 通常与量度相对应。
* **Dimension细分：**&#x200B;每个维度都可以细分为更精细的详细级别。 例如，“月”维度可以划分为一月、二月、三月等。
* **事件序列化：**&#x200B;执行各种措施以防止收集重复事件的过程。请参阅《实施用户指南》中的[事件序列化](../implement/vars/page-vars/events/event-serialization.md)。
* **eVar：**&#x200B;请参阅“转化变量”。
* **事件：**&#x200B;请参阅“成功事件”。
* **有效期限：**&#x200B;在转化变量的上下文中，该值在后端的持续时间。此持久性允许事件在事件点击之前与变量值相关联。请参阅管理用户指南中的[转化变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。
* **流量：** Analysis Workspace 中的一种可视化类型，可显示用户在您的网站上采用的路径。请参阅《Analytics工具指南》中的[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)。
* **全局报表包：**&#x200B;指定给从多个网站收集点击量的报表包的非正式术语。
* **H 代码：** AppMeasurement 的前身。在 Adobe Analytics 的先前版本中，代码版本由“H 版本”（如 H.27.5、H.26 等）来衡量。
* **点击：**&#x200B;发送到 Adobe 数据收集服务器的单个图像请求。页面查看和自定义链接都可以称为点击。
* **图像请求：**&#x200B;用于与 Adobe 数据收集服务器通信的透明 1x1 像素图像。网站用包含数据的长查询字符串请求这个不可见的图像；Adobe 返回不可见的图像并解析收到的查询字符串。
* **Insight:：**&#x200B;可以称为：
   * Data Workbench 之前的名称。
   * 自定义分析，自定义流量变量的历史名称。
* **KPI：**&#x200B;关键绩效指标的缩写。有助于企业了解其网站表现的量度。每个组织分别使用不同的 KPI 来衡量业务的不同方面。请参阅《实施用户指南》中的[创建解决方案设计文档](/help/implement/prepare/solution-design.md)。
* **延迟：**&#x200B;收集数据时和在报表中使用数据时之间的延迟。报表包中的典型延迟时间为 30-90 分钟。请参阅 Technotes 用户指南中的[延迟](/help/technotes/latency.md)。
* **启动：**&#x200B;不再用作术语。Adobe Experience Platform 中的标记的以前简称，Adobe 当前的实施解决方案。请参阅《Adobe Experience Platform 用户指南》中的[标记概述](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)。
* **列表属性：**&#x200B;一种设置，可转化典型流量变量以支持同一点击中的多个值。如果启用了该设置，则任何自定义流量变量都可以成为列表属性。请参阅《实施用户指南》中的[属性](../implement/vars/page-vars/prop.md)。
* **列表变量：**&#x200B;与转化变量分开的不同变量。列表变量支持同一点击中的多个值，并且变量值会在访问中保留，与转化变量类似。组织只能使用三个列表变量。请参阅《实施用户指南》中的[列表](/help/implement/vars/page-vars/list.md)。
* **登录公司：**&#x200B;由您的组织使用的报表包集合。某些组织具有多个适用于该组织不同部分的登录公司。
* **营销渠道：** Adobe Analytics 中的一项功能，可按访客到达网站的方式对点击量进行分类。可使用营销渠道处理规则自定义用于分类点击的逻辑。请参阅《组件用户指南》中的[营销渠道快速入门](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。
* **量度：**&#x200B;包含定量数据的组件类型。量度值通常包含数字，如页面查看次数、访问次数和收入。通常与维度相对应。
* **移动设备应用程序：**&#x200B;也称为&#x200B;**Adobe Analytics [!UICONTROL 功能板]**，该移动设备应用程序允许用户通过移动设备访问直观的记分卡。 记分卡是关键量度和其他组件的集合，这些组件以平铺布局显示，您可以点击它们以获取更详细的划分和趋势报表。iOS 和 Android 操作系统均支持移动设备应用程序。
* **Mobile Services：**&#x200B;已停用的 Adobe 产品，可以在整个 Adobe Experience Cloud 范围内将移动设备应用程序的移动营销功能整合在一起，以便您了解和提高应用程序的用户参与度。
* **多包标记：**&#x200B;向多个报表包发送相同点击的实践。随着虚拟报表包的推出，基本上不再需要这一实践。大多数多包标记工作可帮助满足全局报表包的需求。
* **标准化：**&#x200B;一种组织可视化的方法，采用所有量度并强制按同等比例排列量度，从而更容易比较趋势。
* **发生次数：**&#x200B;一种量度类型，用于显示设置或保留维度项目的点击量。请参阅《组件用户指南》中的[发生次数](/help/components/metrics/occurrences.md)量度。
* **Omniture：**&#x200B;不再用作术语。在 2009 年被 Adobe 收购之前拥有 Adobe Analytics 的组织。
* **路径：**&#x200B;请参阅“流”。
* **页面视图：**&#x200B;一种可增加页面查看次数的点击类型。请参阅《组件用户指南》中的[页面查看](/help/components/metrics/page-views.md)量度。另请参阅“点击”。
* **持久性：**&#x200B;转化变量的抽象概念，允许在变量值和在单独点击中发生的事件之间进行链接。另请参阅“有效期限”。
* **主服务器调用：**&#x200B;图像请求或点击的替代名称，主要用于多包标记和帐单的上下文。当同一点击被发送到多个报表包时，第一个报表包是主服务器调用，而其余报表包是辅助服务器调用。此规则适用于所有点击类型，包括页面查看和链接跟踪。另请参阅“辅助服务器调用”。
* **处理规则：**&#x200B;可以称为：
   * 处理规则，一种在 Admin Console 中使用某些规则更改数据收集的方法。请参阅管理用户指南中的[处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)。
   * 营销渠道处理规则，一组用于确定点击属于哪个营销渠道的规则。请参阅管理用户指南中的[营销渠道处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)。
* **属性：**&#x200B;请参阅“流量变量”。
* **排名报表：**&#x200B;一种报表格式，通常遵循带有量度的维度。此类报表允许您查看排名最前的项目，如网站上查看次数最多的页面。另请参阅“趋势报表”。
* **实时：**&#x200B;在收集配置的变量后立即显示该变量，延迟时间很少甚至没有。请参阅管理用户指南中的[实时报表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)。
* **Report Builder：** Javascript [Report Builder](/help/analyze/report-builder/rb-overview.md)加载项允许您从Adobe Analytics数据构建自定义请求。
* **报表包**：将数据发送到的首要容器。Adobe Analytics 中的所有报表都引用了一个报表包。
* **Reports &amp; Analytics：**&#x200B;此工具[生命周期结束](https://experienceleague.adobe.com/docs/discontinued/using/reports-and-analytics.html)。
* **滚动日期范围：**&#x200B;随时间变化而更改的相对日期范围类型。例如，显示最近 7 天的报表可视为滚动日期范围。另请参阅“静态日期范围”。
* **RSID：**&#x200B;报表包 ID 的缩写。报表包同时具有易记名称和报表包 ID。
* **s.t()：** AppMeasurement 库中发送页面查看图像请求的函数的名称。有些 AppMeasurement 库使用 `s.track()`。请参阅《实施用户指南》中的 [t](../implement/vars/functions/t-method.md)。
* **s<span>.</span>tl()：** AppMeasurement 库中发送链接跟踪图像请求的函数的名称。有些 AppMeasurement 库使用 `s.trackLink()`。请参阅《实施用户指南》中的 [tl](../implement/vars/functions/tl-method.md)。
* **s_code.js：**&#x200B;在 Adobe Analytics 的历史版本中使用的 JavaScript 文件的名称。使用的 JavaScript 文件的当前名称为 AppMeasurement.js。
* **辅助服务器调用：**&#x200B;图像请求或点击的替代名称，主要用于多包标记和帐单的上下文。当同一点击被发送到多个报表包时，列出的第一个报表包之后的所有报表包都是辅助服务器调用。另请参阅“主服务器调用”。
* **区段：**&#x200B;允许您专注于数据的特定子集。请参阅《组件用户指南》中的[分段](/help/components/segmentation/seg-overview.md)。
* **区段容器：**&#x200B;确定要引入多少数据的区段部分。容器可以基于页面查看、访问或访客。请参阅《组件用户指南》中的[分段](/help/components/segmentation/seg-overview.md)。
* **序列化：**&#x200B;请参阅“事件序列化”。
* **服务器调用：**&#x200B;图像请求或点击的替代名称，主要用于帐单上下文。
* **单次存取：**&#x200B;维度只有一个唯一值的访问。只要没有多个唯一值，访问就可以有多个点击。请参阅《组件用户指南》中的[单次存取](/help/components/metrics/single-access.md)量度。另请参阅“跳出”。
* **SiteCatalyst：**&#x200B;不再用作术语。Adobe Analytics 之前的产品名称。
* **解决方案设计文档：**&#x200B;也称为解决方案设计参考或 SDR。由组织维护的内部文档，其中概述了自定义变量的使用方式以及用于填充这些变量的逻辑。请参阅《实施用户指南》中的[创建解决方案设计文档](/help/implement/prepare/solution-design.md)。
* **子关系：**&#x200B;不再用作术语；替换为维度划分。在 Adobe Analytics 的早期版本中，通过子关系可以划分转化变量。请参阅“Analytics工具指南”中的[划分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。
* **成功事件：**&#x200B;用户执行的跟踪操作。贵组织确定要跟踪的事件以及要用于跟踪的成功事件变量。请参阅《组件用户指南》中的[自定义事件](/help/components/metrics/custom-events.md)。
* **支持用户：**&#x200B;请参阅“客户支持代理”。
* **流量变量：**&#x200B;也称为 prop。存储单次点击的自定义值。Adobe Analytics 的早期版本会为属性提供唯一值，但平台经过改进后，在很大程度上降低了自定义流量变量的必要性。Adobe 建议在大多数情况下使用自定义转化变量 (eVar)。请参阅《组件用户指南》中的 [Prop](/help/components/dimensions/prop.md) 维度。
* **趋势报表：**&#x200B;一种报表格式，通常使用一个量度显示多个日期范围。此类报表允许您查看量度一段时间的执行情况。另请参阅“排名报表”。
* **独特访客**：表示访问过您网站的独特个人的数量。一个独特访客可以具有多次访问。请参阅《组件用户指南》中的[独特访客](/help/components/metrics/unique-visitors.md)量度。
* **虚拟报表包：**&#x200B;引用常规报表包并允许细化数据的虚拟数据容器。数据不会发送到虚拟报表包；相反，数据将发送到常规报表包，而虚拟报表包将基于所收集的数据构建。请参阅《组件用户指南》中的[虚拟报表包](/help/components/vrs/vrs-about.md)。
* **访问：**&#x200B;表示在您的网站上发生的独特会话数。请参阅《组件用户指南》中的[访问次数](/help/components/metrics/visits.md)量度。
* **VISTA 规则：** Adobe 应客户复制、解析或过滤服务器端数据的请求创建的自定义逻辑。VISTA 规则通常会产生额外成本。另请参阅“处理规则”。
* **网络信标：**&#x200B;请参阅“图像请求”。
