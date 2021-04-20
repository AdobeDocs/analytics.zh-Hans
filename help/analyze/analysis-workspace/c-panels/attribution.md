---
title: 归因面板
description: 在 Analysis Workspace 中如何使用和解读归因面板。
feature: Attribution
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 65%

---


# 归因面板

[!UICONTROL Attribution]面板是比较各种归因模型构建分析的简单方法。 它是[归因 IQ](../attribution/overview.md) 的一项功能，为您提供专用工作区来使用和比较归因模型。

## 创建归因面板

1. 单击左侧的面板图标。
1. 将[!UICONTROL Attribution]面板拖入您的Analysis Workspace项目。

   ![新建归因面板](assets/Attribution_Panel_1.png)

1. 添加要归因的量度，并添加要归因的对比维度。例如“营销渠道”或自定义维度，如内部促销。

   ![选择维度和量度](assets/attribution_panel2.png)

1. 选择要比较的[归因模型和回顾时间范围](../attribution/models.md)。

1. “归因”面板会返回一组丰富的数据和可视化图表，其中对选定维度和度量进行了归因比较。

   ![归因可视化图表](assets/attr_panel_vizs.png)

## 归因可视化图表

* **总数量度**：报表时间范围内发生的转化总数。这些是在您所选维度中归因的转化。
* **归因比较栏**:以可视方式比较选定维度中每个维度项目的属性转换。每种条形颜色代表一个不同的归因模型。
* **归因比较表**:显示与条形图相同的数据，以表示。选择此表中的不同列或行，会过滤条形图以及面板中的其他一些可视化图表。此表的作用与工作区中任何其他自由格式表的作用相似，允许您添加量度、区段或划分等组件。
* **重叠图**:一个维度图，显示前三个维度项目以及它们共同参与转化的频率。例如，气泡重叠的大小表示当访客出现在两个维度项目中时发生转化的频率。选择相邻自由格式表中的其他行，会更新可视化图表以反映所选内容。
* **性能详细信息**:允许您使用散点图直观地比较最多三个归因模型。
* **趋势性能**:显示顶部维度项目的属性转换趋势。选择相邻自由格式表中的其他行，会更新可视化图表以反映所选内容。
* **流量**:让您了解最常与哪些渠道互动，以及访客旅程中的顺序。

