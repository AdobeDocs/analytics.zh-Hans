---
description: 在 Analysis Workspace 中使用区段。
title: 区段
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
feature: Workspace Basics
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: f107cc32bb42dbc2cde84225867c39bacdbecd9d
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 91%

---


# 区段 {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

可在工作区中创建不同类型的区段，具体取决于这些区段需要达到的复杂程度、是否应将其仅应用于此项目等等。以下总结了各种区段类型：

| 区段类型 | 在何处创建？ | 适用于何处？ | 使用时间 |
| --- | --- | --- | --- |
| 组件列表区段 | 单击 +，这样即转到[区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md) | 您的所有工作区项目 | 对于更复杂的区段、顺序区段 |
| 快速区段 | [快速区段生成器](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | 仅用于项目，但可保存并添加到您的区段列表。 | 灵活地添加/编辑一条或多条规则 |
| 临时区段： |  |  |  |
| - 临时工作区项目区段 | [拖放到项目中的区段放置区域](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md) | 仅用于项目，但可保存并添加到您的区段列表。 | 对于单规则区段 |
| - 基于计算指标的区段 | [计算指标生成器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html?lang=zh-Hans) | 适用于个别计算指标 | 在您的指标定义中应用区段 |
| - 基于 VRS 的区段 | [虚拟报表包生成器](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html?lang=zh-Hans) | 适用于个别虚拟报表包 | 在您的 VRS 定义中应用区段 |

以下是一段关于在 Analysis Workspace 中使用区段的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23977/?quality=12)

## 创建区段 {#section_693CFADA668B4542B982446C2B4CF0F5}

可在 Analysis Workspace 中创建不同类型的区段：

* [快速区段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* [临时区段](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
* 您在区段生成器中创建并最终在区段库中创建的常规组件列表区段（请参阅下文）

### 创建组件列表区段 {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

“组件”菜单下的区段边栏显示
* 您或您的公司创建的区段
* 区段模板，由 Adobe 图标表示：

![](assets/segment_icons.png)

有 2 种方法可创建此类型的区段。他们都带你去 [区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md) 在Adobe Analytics中，您可以找到更多说明。

* 在左边栏中，单击[!UICONTROL “区段”]旁的加号 (+)：

![](assets/create-seg.png)

或

* 转到[!UICONTROL “组件”]>[!UICONTROL “区段”]，然后单击[!UICONTROL “+ 添加”]。


### 应用区段的其他方法 {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

还有其他一些方法也可以将区段应用到自由格式项目中。

| 操作 | 描述 |
|--- |--- |
| 从选定范围中创建区段 | 创建内联区段。该区段只适用于打开的项目并且不能另存为 Analytics 区段。1. 选择行。2. 右键单击选定的内容。3. 单击&#x200B;*从选定范围中创建区段*。 |
| 组件 > 新建区段 | 屏幕上会显示“区段生成器”。有关区段划分的更多信息，请参阅[区段生成器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=zh-Hans)。 |
| “共享”>“共享项目”或“共享”>“策划项目数据” | 在[组织并共享](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hans#concept_4A9726927E7C44AFA260E2BB2721AFC6)中，了解应用到项目中的区段如何用于为收件人提供的共享分析报表。 |
| 使用区段作为维度 | 视频：[在 Analysis Workspace 中使用区段作为维度](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=zh-Hans) |

## 区段 IQ

区段 IQ（也称为“区段比较”）包括以下功能：

* [区段比较面板：](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)区段 IQ 的核心功能。将两个区段拖入面板中，并查看一份全面的报告，其中从统计角度显示了两个受众之间存在的显著差异和重叠。
* [在流失表中比较区段：](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md)通过流失可视化图表，了解不同受众之间的对比情况。

## 更多信息

有关对于 Adobe Analytics 中的区段的深入讨论，请转到[此处](/help/components/segmentation/seg-overview.md)。