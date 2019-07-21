---
title: Adobe Analytics中的报告自定义
description: 了解如何在Adobe Analytics中自定义报告
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# 自定义报告

在第三方平台(如Google Analytics)中，有若干自定义选项可用。这些自定义允许用户创建仪表板、自定义报告、保存的报告和自定义通知。由于Analysis Workspace允许用户从空白画布构建报表，因此大多数自定义功能直接内置于工具中。

此页面假定用户具有使用Analysis Workspace的基本知识。See [Create a basic report in Analysis Workspace for Google Analytics users](reports/create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## 功能板

Analysis Workspace的架构构建类似于仪表板构件的概念。Analysis Workspace中的项目相当于Google Analytics中的仪表板。Analysis Workspace中的可视化相当于Google Analytics中的构件。

### 向项目中添加内容

1. 单击左侧的“可视化”图标，并将所需的可视化拖动到工作区上。
2. 单击左侧的“组件”图标，并将所需的维度和计量指标拖动到可视化上以填充数据。
3. 拖动可视化的边缘以调整其大小，并拖动可视化标题以移动它。

Analysis Workspace中提供所有Google Analytics构件：

* **量度构件** 大约等于摘要编号可视化。
* **时间线构件** 与Line可视化大致相等。
* **Geomap构件** 与地图可视化大致相等。
* **表构件** 与自由表可视化大致相等。
* **饼形构件** 与“圆环”可视化大致相等。
* **Bar构件** 与Bar可视化大致相等。

Analysis Workspace包含更多可视化选项，以最适合报表需求的方式呈现数据。See [Visualizations in Analysis Workspace](../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) in the Analyze User Guide for more information.

### 共享项目

将内容添加到项目后，您可以共享它。

* 要与同事共享项目，请转到“共享”&gt;“共享项目”。收件人是您的组织中具有Adobe Analytics帐户的其他用户。
* 要通过链接共享项目，请转到“共享”&gt;“获取项目链接”。注意，这仍需要在您的组织内登录Adobe Analytics。

### 导出项目

除了PDF之外，Analysis Workspace还提供CSV导出。

1. Click *[!UICONTROL Share]* &gt; *[!UICONTROL Send File Now]*, which opens a modal window.
2. 指定文件类型和收件人。
3. Click [!UICONTROL Send Now].

## 自定义报表

在Google Analytics中创建自定义报告时，所需的字段类似于在工作区中构建可视化的工作流。维度、量度和过滤器定义在平台之间相似。在Analysis Workspace中，将维度和指标从列表中拖动到自由表中，而不是从列表中选择维度和计量指标。

### 自定义报告中的计算指标

自定义报告是Google Analytics中少数几个允许使用计算指标的区域之一。由于Analysis Workspace像画布一样运行，计算得出的度量在任何上下文中均可逆向工作。

创建计算量度：

1. Click the **+** icon near the metric list to open the Calculated Metric Builder.
2. 为您的计算量度提供一个名称并指定一种格式。
3. 将度量组件拖到定义区域中，并使用每个组件之间的下拉菜单指定操作符。
4. 计算得出的量度包含所需的公式后，单击保存以返回您的工作区。
5. 将新定义的计算量度拖动到工作区。

   Learn more about [Calculated Metrics](../../components/c-variables/c-metrics/calculated-metric.md) in the Components user guide.

## 自定义通知

这两个平台提供提醒功能。In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* &gt; *[!UICONTROL Alerts]*. See [Intelligent Alerts](../../components/c-alerts/intellligent-alerts.md) in the Components User Guide for more information.
