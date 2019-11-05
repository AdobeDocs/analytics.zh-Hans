---
title: Adobe Analytics中的报表自定义
description: 了解如何在Adobe Analytics中自定义报告
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# 自定义报表

在Google Analytics等第三方平台中，提供了多个自定义选项。 这些自定义允许用户创建仪表板、自定义报告、保存的报告和自定义警报。 由于Analysis Workspace允许用户从空白画布构建报表，因此大多数自定义操作都直接内置到该工具中。

本页假定用户对使用Analysis Workspace有基本知识。 如 [果您还不熟悉Adobe Analytics中的工具](reports/create-report.md) ，请参阅在Analysis Workspace中为Google Analytics用户创建基本报告。

## 功能板

Analysis Workspace的架构与仪表板构件的概念类似。 Analysis Workspace中的项目与Google Analytics中的仪表板大致相当。 Analysis Workspace中的可视化功能与Google Analytics中的构件大致相当。

### 向项目添加内容

1. 单击左侧的可视化图标，然后将所需的可视化拖动到工作区上。
2. 单击左侧的组件图标，并将所需的维度和度量拖动到可视化上，以用数据填充它。
3. 拖动可视化的边缘以调整其大小，拖动可视化的标题以移动它。

所有Google Analytics构件均在Analysis Workspace中可用：

* 度量 **构件** (Metric Widget)与“摘要编号”可视化大致相等。
* 时间 **轴构件** (Timeline widget)与线可视化(Line visualization)大致相等。
* Geomap构 **件大致等于** “地图”可视化。
* 表构 **件与自由格式表** (Freeform Table)可视化大致相等。
* 饼 **图构件** ，大致等于Donut可视化。
* “条 **形构件** ”大致等于“条形”可视化。

Analysis Workspace包含更多可视化选项，可以以最适合您的报告需求的方式呈现数据。 有关详 [细信息，请参阅《分析用户指南](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) 》中Analysis Workspace中的可视化。

### 共享项目

完成向项目添加内容后，即可共享该内容。

* 要与您的同事共享项目，请转到“共享”&gt;“共享项目”。 收件人是您组织中拥有Adobe Analytics帐户的其他用户。
* 要通过链接共享项目，请转到“共享”&gt;“获取项目链接”。 请注意，这仍需要登录您组织内的Adobe Analytics。

### 导出项目

除PDF外，Analysis Workspace还提供CSV导出功能。

1. 单击“ *[!UICONTROL 共享]* ”(Share *[!UICONTROL )&gt; “]*&#x200B;立即发送文件”(Send File Now)，此时将打开一个模态窗口。
2. 指定文件类型和收件人。
3. Click [!UICONTROL Send Now].

## 自定义报表

在Google Analytics中创建自定义报告时，所需字段与在工作区中构建可视化的工作流类似。 维度、度量和过滤器定义在平台之间相似。 在Analysis Workspace中，维和量度将拖动到自由格式表中，而不是从列表中选择维和量度。

### 自定义报告中的计算量度

自定义报告是Google Analytics中允许使用计算量度的少数几个区域之一。 由于Analysis Workspace的运行方式与画布类似，因此计算的指标可在任何上下文中逆向工作。

创建计算量度：

1. 单击量 **度列表旁的** +图标以打开“计算量度生成器”。
2. 为计算的度量指定名称并指定格式。
3. 将度量组件拖到定义区域，然后使用每个组件之间的下拉列表指定一个运算符。
4. 计算的度量包含所需的公式后，单击保存以返回工作区。
5. 将新定义的计算量度拖动到工作区上。

   了解有关“组 [件”用户指南](/help/components/c-variables/c-metrics/calculated-metric.md) “计算量度”的更多信息。

## 自定义警报

警报在两种平台上均可用。 在Adobe Analytics中，使用标题导航菜单并转到组件 *[!UICONTROL &gt;警]* 报 **。 有关详 [细信息，请参阅](/help/components/c-alerts/intellligent-alerts.md) 《组件用户指南》中的智能警报。
