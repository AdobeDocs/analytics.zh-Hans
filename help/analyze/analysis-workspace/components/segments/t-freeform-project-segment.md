---
description: 在 Analysis Workspace 中使用区段。
title: 区段
feature: Segmentation
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 81%

---


# 区段 {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

可在工作区中创建不同类型的区段，具体取决于这些区段需要达到的复杂程度、是否应将其仅应用于此项目等等。以下总结了各种区段类型：

| 区段类型 | 在何处创建？ | 适用于何处？ | 使用时间 |
| --- | --- | --- | --- |
| 组件列表区段 | 单击 +，这样即转到[区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md) | 您的所有工作区项目 | 对于更复杂的区段、顺序区段 |
| 快速区段 | [快速区段生成器](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | 仅用于项目，但可保存并添加到您的区段列表。 | 可用于临时单规则区段（通过拖放），或添加/编辑多个规则（通过单击“区段”图标） |
| 基于计算量度的区段 | [计算指标生成器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html?lang=zh-Hans) | 适用于个别计算指标 | 在您的指标定义中应用区段 |
| 基于虚拟报表包的区段 | [虚拟报表包生成器](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html?lang=zh-Hans) | 适用于个别虚拟报表包 | 在您的虚拟报表包定义中应用区段 |

## 视频

>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在Analysis Workspace中使用区段](https://video.tv.adobe.com/v/23977?quality=12&learn=on){target="_blank"}来演示视频。

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [查找和创建演示视频的区段](https://video.tv.adobe.com/v/334092?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[区段中的滚动日期范围](https://video.tv.adobe.com/v/25403?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


## 创建区段 {#section_693CFADA668B4542B982446C2B4CF0F5}

可在 Analysis Workspace 中创建不同类型的区段：

* [快速区段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* 您在区段生成器中创建的最终位于区段库中的常规组件列表区段（见下文）

### 创建组件列表区段 {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

“组件”菜单下的区段边栏显示

* 您或您的公司创建的区段
* 区段模板，由Adobe![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg)图标表示：


有 2 种方法可创建此类型的区段。这两种方法都带您进入 Adobe Analytics 中的[区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md)，您可以在其中查找详细说明。

* 在左边栏中，单击[!UICONTROL “区段”]旁的加号 (+)：

![](assets/create-seg.png)

或

* 转到[!UICONTROL “组件”]>[!UICONTROL “区段”]，然后单击[!UICONTROL “+ 添加”]。


### 应用区段的其他方法 {#section_10FF2E309BA84618990EA5B473015894}


>[!BEGINSHADEBOX]

请参阅演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [应用区段的其他方法](https://video.tv.adobe.com/v/30994?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

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
