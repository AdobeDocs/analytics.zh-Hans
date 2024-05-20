---
description: 有两种方式可使用 Analysis Workspace 中的指标。
title: Analysis Workspace 中的指标
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: 564fb1cd65daf7efb03e1258ee378939f37c9426
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 94%

---

# 指标

指标允许您量化 Analysis Workspace 中的数据点。它们最常用作可视化中的列，并与维度相关联。

## 指标类型

Adobe 提供了多种类型的指标，可供在 Analysis Workspace 中使用：

* **标准指标**：您在项目中使用的大多数指标都是标准指标。相关例子包括[页面浏览量](/help/components/metrics/page-views.md)、[收入](/help/components/metrics/revenue.md)或者[自定义事件。](/help/components/metrics/custom-events.md)有关更多信息，请参阅组件用户指南中的[指标概述。](/help/components/metrics/overview.md)

  ![标准指标](assets/standard-metric.png)

* **计算指标**：基于标准指标、静态数字或算法函数的由用户定义的指标。用户定义的计算指标会在可用组件列表中显示一个计算器图标。有关更多信息，请参阅组件用户指南中的[计算指标概述。](/help/components/c-calcmetrics/cm-overview.md)

  ![计算指标](assets/calculated-metric.png)

* **计算指标模板**：Adobe 定义的指标，其行为类似于计算指标。您可以在 Workspace 项目中按原样使用它们，或保存副本以自定义其逻辑。计算指标模板会在可用组件列表中显示一个 Adobe 图标。

  ![计算指标模板](assets/calculated-metric-template.png)

## 在 Analysis Workspace 中使用指标

指标可以在 Analysis Workspace 中以各种方式使用。有关如何将量度和其他类型的组件添加到Analysis Workspace的信息，请参阅 [在Analysis Workspace中使用组件](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## 计算指标

通过计算指标，您可以使用简单的运算符或统计函数轻松查看指标之间的相互关系。可通过以下几种方式创建计算指标：

* 单击左侧组件列表下“指标”标题旁边的加号图标。
* 导航到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 计算指标]** > **[!UICONTROL 添加]**。
* 选择一个或多个标题列单元格时，右键单击列标题 > **[!UICONTROL 从所选内容创建指标]**。此选项会自动为您创建计算指标，而无需使用计算指标规则构建器。

[计算指标：无实施指标](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=zh-Hans) (3:42)

## 比较不同归因模型的指标

如果您希望轻松快速地将一个归因模型与另一个进行比较，请右键单击某个指标并选择&#x200B;**[!UICONTROL 比较归因模型]**：

![比较归因模型](assets/compare-attribution.png)

此快捷键可让您快速、轻松地将一个归因模型与另一个归因模型进行比较，而无需将归因模型拖动到某个指标中且不必对其进行两次配置。

## 使用[!UICONTROL 累积平均]函数应用指标平滑

以下是一段关于该主题的视频：

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)
