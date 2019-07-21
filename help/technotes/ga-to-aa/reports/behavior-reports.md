---
title: Adobe Analytics中的行为报告
description: 了解如何在Adobe Analytics中创建行为报告
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# 行为报告

行为报告显示用户如何与您的站点交互的信息。

此页面假定用户具有使用Analysis Workspace的基本知识。See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## 行为流程

可使用流可视化重新创建行为流报告。

1. 单击左侧的可视化图标，并将流动可视化拖动到自由表上方的工作区上
2. Locate the **Page** dimension, then click the Arrow icon to reveal page values. 尺寸值为黄色。
3. 找到所需的页面值以开始，并将其拖动到中心中标记为“维度或项目”的空间中
4. 此流报告为交互式报告。单击任意值可将流展开到后续或之前的页面。使用右键单击菜单展开或折叠列。也可以在同一流程报告中使用不同的维度。

![流报告](../assets/flow.png)

## 站点内容-所有页面

页面报告显示网站上各个页面的性能。

1. In the Components menu, locate the **Pages** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

作为替代选择，Adobe提供了几个预创建的名为模板的工作区。内容消耗(Web)模板为所有页面报表提供类似值。

1. Click *[!UICONTROL Project]&gt;[!UICONTROL New]*, which opens a modal window with project options.
2. 单击内容消耗(Web)模板，然后单击创建。

## 站点内容-内容下拉列表

内容drzzown报告允许您按URL结构查看页面流量。需要额外的实施才能在Analysis Workspace中使用。Adobe建议与实施顾问合作，以确保准确收集此数据。

## 站点内容-登陆页面

登陆页面报告显示您网站上的主要登陆页面。Landing pages are available in Analysis Workspace as the **Entry Page** dimension.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Visits** metric for this dimension.

## 站点内容-退出页面

退出页面报告显示成为个人访问最后一页的顶部页面。它位于同一名称下的Analysis Workspace中。

1. In the Components menu, locate the **Exit Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Visits** metric for this dimension.

## 站点速度报告

站点速度报告显示页面加载速度，从而增加页面加载时间。

此功能需要在两个平台上进行额外的实现；Adobe建议与实施顾问合作，确保对Analysis Workspace正确配置此数据。[性能计时插件](../../../implement/js-implementation/plugins/performancetiming.md) 通常分配给eVar以获取Adobe Analytics中的性能数据。

## 站点搜索报告

站点搜索报告提供有关访客如何使用站点内部搜索功能的洞察。

此功能需要在两个平台上进行额外的实现；Adobe建议与实施顾问合作，确保对Analysis Workspace正确配置此数据。通常，内部搜索词从查询字符串参数中提取，并放入eVar进行报告。

## 活动报告

活动在Google和Adobe Analytics之间有一些主要的结构性差异。这两种方法都需要额外的实施更改以在其各自的平台上正常工作。

* 在Google Analytics中，活动在您的实施中被定义为文本。活动有类别、操作和标签。
* 在Adobe Analytics中，首先在Admin Console中设置活动，然后将其分配给标识符。此标识符用于实施代码。例如：
   1. 您可以将Admin Console中的event设置为“Registrations”。
   2. 在您的实施中，您将在注册确认页面上的活动变量中包含event1。每次显示注册确认页面时，活动将增加1。
   3. 在Analysis Workspace中，“注册”显示为可在任何报告中使用的量度。

由于此功能需要实施更改，Adobe建议与实施顾问合作以确保对Analysis Workspace正确配置数据。

## Publisher报告

与Google需要与Google广告管理器的连接相似，Adobe提供专门的产品来提供称为Adobe Advertising Cloud的洞察。如果您的组织有意使用此产品，请与贵组织的客户经理联系。
