---
description: 您可以在整个Analytics中使用Adobe Audience Manager受众维度。 集成的区段是名为“受众 ID”和“受众名称”的新 Analytics 维度，并且可以像 Analytics 收集的任何其他维度一样使用。在数据馈送中，受众 ID 存储在“mc_audiences”列中。这些维度当前在 Data Workbench 或 Livestream 中不可用。有关如何利用受众维度的一些示例包括
solution: Experience Cloud
title: 在 Analytics 中使用受众数据
feature: Audience Analytics
exl-id: c1c0a9de-4051-4073-82c1-5615b0f01fa9
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 89%

---

# 在 Analytics 中使用受众数据

您可以在整个Analytics中使用Adobe Audience Manager受众维度。 集成的区段是名为“受众 ID”和“受众名称”的新 Analytics 维度，并且可以像 Analytics 收集的任何其他维度一样使用。在数据馈送中，受众 ID 存储在“mc_audiences”列中。这些维度当前在 Data Workbench 或 Livestream 中不可用。有关如何利用受众维度的一些示例包括：

## Analysis Workspace {#workspace}

在Analysis Workspace中，Adobe Audience Manager区段显示为两个维度。

1. 转至&#x200B;**[!UICONTROL 工作区]**。
1. 从&#x200B;**[!UICONTROL 维度]**&#x200B;列表中，选择维度&#x200B;**[!UICONTROL 受众 ID]** 或&#x200B;**[!UICONTROL 受众名称]**。名称即是一种易记的 ID 分类。

   ![](assets/aw-mcaudiences.png)

## 区段比较 {#compare}

[区段比较](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)可发现两个区段间在统计上的最显著差异。区段比较可通过以下两种方式来使用受众数据：1) 作为正在进行比较的 2 个区段，2) 作为“排名最前的维度项目”表中的项目。

1. 转至&#x200B;**[!UICONTROL 工作区]**&#x200B;并从左边栏中选择&#x200B;**[!UICONTROL 区段比较]**&#x200B;面板。

1. 在&#x200B;**[!UICONTROL 组件]**&#x200B;菜单中搜索[!UICONTROL 受众名称]。

1. 打开[!UICONTROL 受众名称]，以便显示相关的维度项目。
1. 将需要比较的受众拖至区段比较生成器中。
1. （可选）：您还可以放入其他维度项目或区段中，最多可比较 2 个。
1. 单击&#x200B;**[!UICONTROL 生成]**。

   受众 ID 和名称维度将自动显示在“排名最前的维度项目”表中，因为它们是两个正在进行比较的区段的额外轮廓数据。

   ![](assets/aud-segcompare.png)

## Analysis Workspace 中的客户历程（流量） {#flow}

Adobe Audience Manager区段数据是按点击传递到Analytics中的，表示访客在该时间点所具有的受众成员资格。 这意味着，访客可能归属于一个区段（例如“感知”），然后又有资格访问另外一个获得授权的区段（例如“注意事项”）。您可以在 Analysis Workspace 中使用[流量](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)显示访客在各受众之间的历程。

1. 转至&#x200B;**[!UICONTROL 工作区]**&#x200B;并从左边栏中选择&#x200B;**[!UICONTROL 流量]**&#x200B;可视化。

1. 将[!UICONTROL 受众名称]维度拖至流量生成器中。
1. 单击&#x200B;**[!UICONTROL 生成]**。
1. （可选）将任何其他维度拖至流量可视化中以创建[维度间流量](/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)。

![](assets/flow-aamaudiences.png)

受众还可用于[流失可视化](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)。

## Analysis Workspace 中的维恩可视化 {#venn}

[维恩可视化](/help/analyze/analysis-workspace/visualizations/venn.md)显示最多 3 个区段之间的叠加。

1. 转至&#x200B;**[!UICONTROL 工作区]**&#x200B;并从左边栏中选择&#x200B;**[!UICONTROL 维恩]**&#x200B;可视化。

1. 在组件菜单中搜索[!UICONTROL 受众名称]。
1. 打开[!UICONTROL 受众名称]以便显示相关的维度项目。
1. 将需要比较的受众拖至维恩生成器中。
1. （可选）：您还可以放入其他维度项目或区段，最多可比较 3 个。
1. 单击&#x200B;**[!UICONTROL 生成]**。

![](assets/venn-viz.png)

## 区段生成器 {#builder}

您可以整合 Analytics [区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md)中的受众维度，以及 Analytics 收集到的行为信息。

1. 转至&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 区段]**。
1. 单击&#x200B;**[!UICONTROL 添加]**&#x200B;以创建一个新区段。
1. 在命名区段后，将[!UICONTROL 受众名称]维度拖至定义面板中。
1. （可选）：向区段添加其他标准。
1. 保存该区段。

   ![](assets/aud-segbuilder.png)

