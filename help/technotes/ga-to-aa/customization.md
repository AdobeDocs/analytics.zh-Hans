---
title: Adobe Analytics 中的报表自定义
description: 了解如何在 Adobe Analytics 中自定义报表
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 75%

---


# 自定义报表

在 Google Analytics 等第三方平台中，提供了多个自定义选项。这些自定义允许用户创建功能板、自定义报表、保存的报表和自定义警报。由于 Analysis Workspace 允许用户从空白画布构建报表，因此大多数自定义操作都直接内置到工具中。

This page assumes the user has a basic knowledge of using [!UICONTROL Analysis Workspace]. 如果您还不熟悉 Adobe Analytics 中的工具，请参阅[在 Analysis Workspace 中为 Google Analytics 用户创建基本报表](reports/create-report.md)。

## 功能板

The [!UICONTROL Analysis Workspace] architecture is built similar to the concept of dashboard widgets. Projects in [!UICONTROL Analysis Workspace] are the approximate equivalent to dashboards in Google Analytics. Visualizations in [!UICONTROL Analysis Workspace] are the approximate equivalent of widgets in Google Analytics.

### 将内容添加到项目

1. Click the [!UICONTROL Visualizations] icon on the left and drag the desired visualization onto the workspace.
2. Click the [!UICONTROL Components] icon on the left and drag the desired dimensions and metrics onto the visualization to populate it with data.
3. 拖动可视化的边缘以调整其大小，然后拖动可视化的标题进行移动。

All Google Analytics widgets are available in [!UICONTROL Analysis Workspace]:

* **量度小组件**&#x200B;大致相当于“摘要编号”可视化。
* **时间线小组件**&#x200B;大致相当于“折线图”可视化。
* **Geomap 小组件**&#x200B;大致相当于“地图”可视化。
* **表格小组件**&#x200B;大致相当于“自由格式表”可视化。
* **饼图小组件**&#x200B;大致相当于“圆环图”可视化。
* **条形图小组件**&#x200B;大致相当于“条形图”可视化。

[!UICONTROL Analysis Workspace 包含更多可视化选项，可通过最适合您报表需求的方式呈现数据。]有关更多信息，请参阅分析用户指南中的 [Analysis Workspace 中的可视化](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。

### 共享项目

完成向项目添加内容后，即可共享该内容。

* To share the project with your colleagues, go to **[!UICONTROL Share > Share Project]**. 收件人是您组织中拥有 Adobe Analytics 帐户的其他用户。
* To share your project via a link, go to **[!UICONTROL Share > Get Project Link]**. 请注意，这仍需要您登录组织内的 Adobe Analytics。

### 导出项目

In addition to PDF, [!UICONTROL Analysis Workspace] offers a CSV export.

1. 单击&#x200B;*[!UICONTROL 共享]* > *[!UICONTROL 立即发送文件]*，此时将打开一个模式窗口。
2. 指定文件类型和收件人。
3. 单击[!UICONTROL 立即发送]。

## 自定义报表

在 Google Analytics 中创建自定义报表时，所需字段与在工作区中构建可视化的工作流类似。两平台中的维度、量度和过滤器定义相似。在 Analysis Workspace 中，将维度和量度拖动到自由格式表中，而不是从列表中选择维度和量度。

### 自定义报表中的计算量度

自定义报表是 Google Analytics 中允许使用计算量度的少数几个区域之一。由于 Analysis Workspace 的运行方式与画布类似，因此计算量度可在任何上下文中逆向工作。

创建计算量度：

1. Click the **+** icon near the metric list to open the [!UICONTROL Calculated Metric Builder].
2. 为计算度量提供一个名称并指定格式。
3. 将量度组件拖到定义区域，然后使用每个组件之间的下拉列表指定一个运算符。
4. 计算量度包含所需的公式后，单击“保存”以返回工作区。
5. 将新定义的计算量度拖动到工作区上。

   您可在组件用户指南中了解有关[计算量度](/help/components/c-calcmetrics/cm-overview.md)的更多信息。

## 自定义警报

警报在两种平台上均可用。在 Adobe Analytics 中，使用标题导航菜单，转到&#x200B;*[!UICONTROL 组件]* > *[!UICONTROL 警报]*。有关更多信息，请参阅组件用户指南中的[智能警报](/help/components/c-alerts/intellligent-alerts.md)。
