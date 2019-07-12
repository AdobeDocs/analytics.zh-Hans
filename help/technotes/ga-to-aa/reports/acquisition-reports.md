---
title: Adobe Analytics中的客户获取报告
description: 了解如何使用Analysis Workspace创建基于客户赢取的报告。
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# 客户获取报告

客户获取报告显示您如何获得网站访客。

In Adobe Analytics, these reports are known as **Marketing Channels**. 它们需要一些基本的初始设置，但允许更多的渠道自定义视图。

> [!IMPORTANT]
>
> 设置您的营销渠道处理规则以使用这些报告。See [Getting Started with Marketing Channels](../../../components/c-marketing-channels/c-getting-started-mchannel.md) for information on how to best configure Marketing Channels in your organization.

此页面假定用户具有使用Analysis Workspace的基本知识。See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## 所有流量-渠道

显示访客访问网站时使用的所有渠道的汇总视图。

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## 所有流量-树地图

显示渠道流量的轨迹。此报告类似于所有流量-渠道，但以其他方式显示。

1. 单击左侧的“可视化”图标，并将Treemap可视化拖动到空自由表单表上方的工作区上。
2. Click the Components icon on the left, then drag the **Marketing Channel** dimension onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.
4. 请注意，其他指标会创建额外的树。如果只需要一个treemap：
   1. 单击所需指标的顶部单元格以表示treemap。
   2. 按住Shift键并单击同一量度列的最后一个单元格，可突出显示列蓝色。如果正确完成，可视化中就存在一个treemap。
   3. 单击treemap可视化右上角的彩色点，然后单击复选框“锁定选择”。

树地图可应用于任何维度，而不仅仅是营销渠道。

## 所有流量-源/中级

源和中级报表显示驱动访问网站流量的域。

* **源** 主要维度在Analysis Workspace中作为 **引用域** 维度可用。
* **中** 主要维度在Analysis Workspace中作为 **参照类型** 维度可用。
* **关键字** 主要维度在Analysis Workspace中作为 **搜索关键字** 维度可用。

1. 在组件菜单中，找到上面所需的维度，并将其拖动到标记为“在此处放置一个维度”的大型自由表格区域。
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

有关其各自维度的更多信息，请参阅组件用户指南中的以下页面：

* [反向链接域](../../../components/c-variables/dimensionslist/reports-referring-domains.md)
* [反向链接类型](../../../components/c-variables/dimensionslist/reports-ref-types.md)
* [搜索关键词](../../../components/c-variables/dimensionslist/reports-search-keywords.md)

## 所有流量-引用

* **源** 主要维度在Analysis Workspace中作为 **引用域** 维度可用。
* **登陆页面** 主要维度在Analysis Workspace中作为 **进入页面** 维度可用。

1. In the components menu, locate the **Referring Domain** or **Entry Page** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Referring Domain](../../../components/c-variables/dimensionslist/reports-referring-domains.md) dimension in the Components user guide for more information.

## Google Ads报告和搜索控制台报告

Adobe使用Analysis Workspace中称为Advertising Analytics的功能引入来自包括Google在内的多个平台的广告和搜索数据。

广告分析功能需要配置来返回数据。See [Advertising Analytics Help](../../../integrate/c-advertising-analytics/overview.md) for details on how to enable these additional dimensions in Analysis Workspace.

## Social 报表

社交报告提供与其各自的行为报告相似的信息，但社交网络的上下文除外。通过将维度与区段相结合，可以在Analysis Workspace中使用此数据。

有时，访客在同一会话中通过多个渠道访问您的站点。例如，访客单击社交媒体页面，几分钟后访问搜索引擎访问您的网站。在这些情况下，非社交域可显示在此报告中。如果您希望排除非社交域，请按访问排序报告，或创建区段副本以基于点击而不是访问。See [Segmentation Containers](../../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### 社交-网络引用

“网络引用”报告显示哪些社交网络域驱动访问您的站点。This data is available in Analysis Workspace using the **Referring Domain** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Referring Domain** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled &#39;Drop a segment here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### 社交-登陆页面

登陆页面报告显示访客通过社交网络单击链接后到达的页面。This data is available in Analysis Workspace using the **Entry Page** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled &#39;Drop a segment here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### 社交-转化

“转换”报告显示社交网络上下文中的电子商务数据。在这两种平台上都需要执行额外的实施；Adobe建议与实施顾问合作，确保对Analysis Workspace正确配置此数据。

### 社交-插件

插件报告显示访客如何与您的站点上的嵌入社交媒体插件交互。需要额外的实施才能在Analysis Workspace中使用。Adobe建议与实施顾问合作，以确保准确收集此数据。

### 社交-用户流

“用户”流报告显示访问社交网络的访客上下文中的路径数据。

1. 单击左侧的可视化图标，并将流动可视化拖动到自由表上方的工作区上
2. Click the Components icon on the left, then drag the **Visits from Social Sites** segment onto the small area just above the flow visualization labeled &#39;Drop a Segment here&#39;.
3. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. 尺寸值为黄色。
4. 找到所需的页面值以开始，并将其拖动到中心中标记为“维度或项目”的空间中
5. 此流报告为交互式报告。单击任意值可将流展开到后续或之前的页面。使用右键单击菜单展开或折叠列。也可以在同一流程报告中使用不同的维度。

## 营销活动-全部

The campaigns report is available in Analysis Workspace using the **Tracking Code** dimension. 请注意，使用跟踪代码维度需要额外的实施来收集数据。

可以使用自定义变量(eVar)在Adobe Analytics中收集UM参数。Adobe建议与实施顾问合作，确保在Adobe Analytics中准确收集跟踪代码值。

1. In the Components menu, locate the **Tracking Code** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## 营销活动-付费关键字

付费关键字报告显示在访客单击搜索引擎中付费搜索链接后每个关键字的执行方式。**搜索关键字-付费** 维度在Analysis Workspace中可用，但需要一次性设置付费搜索检测以收集数据。See [Paid Search Detection](../../../admin/admin/paid-search-detection/paid-search-detection.md) in the Admin user guide for setup details.

1. In the Components menu, locate the **Search Keyword - Paid** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## 营销活动-有机关键字

有机关键字报表显示在访客单击搜索引擎中的有机搜索链接后每个关键字的执行方式。**搜索关键字-自然** 尺寸在Analysis Workspace中可用。请注意，如果未设置付费搜索检测，则此维度同时收集付费和自然关键字。

1. In the Components menu, locate the **Search Keyword - Natural** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## 成本分析

此报告显示您的付费营销渠道的访问、成本和收入绩效数据。Adobe提供专门的产品来提供称为Adobe Advertising Cloud的洞察。如果您的组织有意使用此产品，请与贵组织的客户经理联系。
