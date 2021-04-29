---
title: 分析营销渠道
description: 了解如何在工作区中使用营销渠道维度。
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
translation-type: tm+mt
source-git-commit: 7202a49dda7c3ef4f4b535476d3cf637b9e9f7f6
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 86%

---

# 分析营销渠道

>[!NOTE]
>
>为最大限度地提高Attribution IQ和Customer Journey Analytics营销渠道的效率，我们发布了一些[修订的最佳实践](/help/components/c-marketing-channels/mchannel-best-practices.md)。

您可能希望了解哪些营销渠道以及与谁合作最有效，从而更好地集中您的精力，并从营销资金中获得更好的回报。在 Adobe Analytics 中，工作区中的营销渠道维度和量度是帮助您跟踪不同渠道对订单、收入等的影响的工具之一。并为您提供有用的渠道分析。以下是您可以使用的与营销渠道相关的维度和量度：

![](assets/mc-dims.png)

| 维度/量度 | 定义 |
| --- | --- |
| 营销渠道 | 这是建议使用的营销渠道维度。可在运行时对其应用归因 IQ 模型。此维度与“最近联系渠道”维度的行为相同，但采用不同的方式标记，以防止在与其他归因模型一起使用时产生混淆。 |
| 最近联系渠道 | 旧版维度，带有预应用的最近联系归因模型且不可更改。 |
| 首个联系渠道 | 旧版维度，带有预应用的首个联系归因模型且不可更改。 |
| 营销渠道实例 | 此量度衡量在图像请求中定义营销渠道的次数，包括标准页面查看和自定义链接调用。不包括持续得到的值。 |
| 新参与 | 此量度与实例类似，但仅当在图像请求中定义了首次联系营销渠道时，此量度才递增。 |

## 基本分析

此自由格式表显示每个营销渠道的在线订单、在线收入和转化率量度：

![](assets/mc-viz1.png)

在此，您可以在圆环图中看到每个营销渠道的在线订单和在线收入：

![](assets/mc-viz2.png)

此折线图显示一段时间内各渠道在线订单的趋势：

![](assets/mc-viz3.png)

## 高级分析

营销渠道详细信息可更深入地挖掘每个渠道，以向您显示特定促销活动、位置等。您可以将每个营销渠道细分为详细信息：

![](assets/mc-viz4.png)

## 应用归因模型

您可以使用[归因 IQ](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/panels/attribution/use-attribution.html)，即时应用不同的归因模型：

![](assets/mc-viz5.png)

请注意当您应用不同的归因模型时，同一量度（在线订单）是如何生成不同结果的。

## 交叉表营销分析

使用传统的“首次触摸”渠道和“最后触摸”渠道，您可以在渠道交互中获得有用的视图:

![](assets/mc-viz6.png)

通过本视频了解交叉表营销分析的详情：[在 Analysis Workspace 中使用交叉表分析来了解基本营销归因](https://docs.adobe.com/content/help/zh-Hans/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html)。
