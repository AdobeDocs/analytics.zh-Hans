---
title: Adobe Analytics中的受众报告
description: 了解如何使用Analysis Workspace创建基于受众的报告。
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# 受众报告

受众报告显示有关访问您的站点的人员类型的信息。

此页面假定用户具有使用Analysis Workspace的基本知识。See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## 活动用户

活动用户显示在前1、7、14或28天内站点的累计用户数。虽然Adobe没有在Google Analytics中使用准确的计算，但您可以使用衡量标准唯一访客来根据选定的日期范围查看将重复的用户计数。

要获得唯一访客的折线图，请执行以下操作：

1. 单击左侧的“可视化”图标，并将Line可视化拖动到空自由表单表上方的工作区上。
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the smaller space labeled &#39;Drop a Metric here&#39;.
3. If different granularity is desired, drag the desired date range (e.g. **Day**, **Week**, **Month**, etc.) 位于现有日期维度标题的顶部。

See [Unique Visitors](../../../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide for details on how Adobe calculates unique visitors.

## 生命周期值

终身价值是一项功能，需要在这两个平台上进行额外的专门实施。Adobe建议与实施顾问合作获取此数据。

## 同类群组分析

群组分析显示相同用户返回您网站的频率。

要创建同期表，请执行以下操作：

1. 单击左侧的可视化图标，并将Cohr表可视化拖动到工作区上。
2. Click the Components icon on the left, then drag the **Visits** metric onto both the Inclusion Criteria and Return Criteria.
3. 单击生成。

See [Cohort Analysis](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analysis Workspace user guide for details on additional customizations to the cohort visualization.

## 受众

Google Analytics中的受众报告需要设置受众。受众还需要通过Adobe Audience Manager在Adobe中进行配置。有关更多信息，请参阅Adobe Audience Manager用户指南。

## 用户资源管理器

用户资源管理器报告允许分析师通过anony化的标识符查看单独访问。Adobe不会在数据馈送之外显示后端标识符，这些标识符是数据的点击级别数据导出。

* 如果在Analysis Workspace中需要此数据，可以与实施顾问合作，将anonyMered唯一标识符cookie值传递给eVar。请注意，这仅适用于由每月不超过100万个唯一访客组成的小规模实施。
* If this data is desired within data feeds, the concatenated columns `visid_high` and `visid_low` are the most common way to identify unique visitors. Learn more about [Data Feeds](../../../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.

## 人口统计和兴趣报告

人口统计和兴趣数据提供有关站点用户的年龄、性别和兴趣的信息。这些数据由Google通过其跨站点跟踪功能收集。

人口统计和兴趣数据不会由Adobe自动收集。但是，如果您的组织获得此数据，您可以使用Adobe Experience Cloud Platform内的客户属性。它允许完全控制按属性组织数据，并不仅限于人口统计或兴趣。

有关更多信息，请参阅客户属性帮助。

## 地理-语言

地理语言报告按访客浏览器中的语言设置显示站点流量。

要创建语言报表，请执行以下操作：

1. In the Components menu, locate the **Language** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Language](../../../components/c-variables/dimensionslist/reports-languages.md) dimension in the Components user guide for more information.

## 地理位置-位置

地理位置报告提供全球地图视图，按国家/地区划分数据。

要创建地理位置报告，请执行以下操作：

1. 单击左侧的“可视化”图标，并将“地图”可视化拖动到空自由表单表上方的工作区上。
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the space labeled &#39;Add Metric&#39;.
3. 单击生成。

如果除了地图之外还需要表格：

1. In the Components menu, locate the **Countries** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See [Geosegmentation](../../../components/c-variables/dimensionslist/reports-geosegmentation.md) dimensions in the Components user guide for more information.

## 行为-新增与退回

新的与返回报告针对第一次会话(新访问)与后续会话(回访)提供简化的视图。

要创建新的访问次数报告，请执行以下操作：

1. In the components menu, locate the **First Time Visits** segment and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;. Note that **First Time Visits** is a segment, while Workspace typically uses dimensions to represent rows.
2. Locate the **Return Visits** segment and drag it on top of the Segments row header. 这会将区段添加为“首次访问次数”下面的维度，从而允许轻松比较。
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

如果还需要折线图：

1. 单击左侧的可视化图标，并将Line可视化拖动到自由表上方的工作区上
2. 在自由表中，使用Ctrl并单击(Windows)或cmd并单击(Mac)，以突出显示表单行。这会使这两种趋势出现在线可视化中。
3. 单击线条可视化左上角的彩色小圆点，然后单击复选框“锁定选择”。

## 行为-频率和新近度

The frequency &amp; recency report is approximately equal to the **Visit Number** dimension in Analysis Workspace.

1. In the components menu, locate the **Visit Number** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Visit Number](../../../components/c-variables/dimensionslist/reports-visitor-number.md) dimension in the Components user guide for more information.

## 行为-参与度

The engagement report is approximately equal to the **Time Spent per Visit - Bucketed** dimension.

1. In the components menu, locate the **Time Spent per Visit - Bucketed** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Time Spent per Visit](../../../components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dimension in the Components user guide for more information.

## 技术-浏览器和操作系统

浏览器和操作系统报告中有多个主要维度。

* **浏览器** 主要维度也在Analysis Workspace中作为维度提供。
* **操作系统** 主要维度也在Analysis Workspace中作为维度提供。
* **屏幕分辨率** 主要维度在Analysis Workspace中作为 **监视器分辨率** 维度可用。
* **“屏幕颜色** ”主要维度在Analysis Workspace中作为 **“色深** ”尺寸可用。
* **Flash版本** 主要维度在Adobe Analytics中不可用，但如果需要，可以由eVar收集此数据。

1. 在组件菜单中，找到上面所需的维度，并将其拖动到标记为“在此处放置一个维度”的大型自由表格区域。
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

有关其各自维度的更多信息，请参阅组件用户指南中的以下页面：

* [浏览器](../../../components/c-variables/dimensionslist/reports-browsers.md)
* [操作系统](../../../components/c-variables/dimensionslist/reports-operating-system.md)
* [监视器分辨率](../../../components/c-variables/dimensionslist/reports-technology.md)
* [颜色深度](../../../components/c-variables/dimensionslist/reports-color-depth.md)

## 技术-网络

The network report is approximately equal to the **Domain** dimension.

1. In the components menu, locate the **Domain** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Domain](../../../components/c-variables/dimensionslist/reports-domains.md) dimension in the Components user guide for more information.

## 移动-概述

The mobile overview report is approximately equal to the **Mobile Device Type** dimension. 请注意，“其他”值与桌面流量等效。

1. In the components menu, locate the **Mobile Device Type** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device Type](../../../components/c-variables/dimensionslist/reports-device-types.md) dimension in the Components user guide for more information.

## 移动-设备

The mobile devices report is approximately equal to the **Mobile Device** dimension.

1. In the components menu, locate the **Mobile Device** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device](../../../components/c-variables/dimensionslist/reports-devices.md) dimension in the Components user guide for more information.

## 自定义

自定义报告是按实施进行定义的。与贵组织的Analytics管理员和/或实施顾问共同解释这些报告。Typically an organization maintains a [Solution Design Document](../../../implement/prepare/solution-design.md) to keep track of custom variable values and how they are populated.

## 基准测试

基准测试报告允许您查看数据的facet与行业平均值的差异。目前，Adobe不会在其客户之间共享基准数据。

## 用户流

流报告在这两个平台上可用。要创建流报告，请执行以下操作：

1. 单击左侧的可视化图标，并将流动可视化拖动到自由表上方的工作区上
2. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. 尺寸值为黄色。
3. 找到所需的页面值以开始，并将其拖动到中心中标记为“维度或项目”的空间中
4. 此流报告为交互式报告。单击任意值可将流展开到后续或之前的页面。使用右键单击菜单展开或折叠列。也可以在同一流程报告中使用不同的维度。
