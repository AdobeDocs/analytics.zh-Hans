---
description: 在 Analysis Workspace 中划分维度和维度项目。
keywords: Analysis Workspace
title: 划分维度
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 92%

---


# 划分维度

在 Analysis Workspace 中划分维度和维度项目。

为了满足您的特定需求，划分数据的方法可以不受限制；您可以使用相关的量度、维度、区段、时间线以及其他分析划分值来构建查询。

1. [创建项目](/help/analyze/analysis-workspace/home.md)，其中包含一个数据表。
1. 在数据表中，右键单击某个行项目，然后选择&#x200B;**[!UICONTROL 划分]** > *`<item>`*。

   ![步骤结果](assets/fa_data_table_actions.png)

   您可以按维度项目或受众区段，在选定的时间期限内划分量度。此外，您还可以进一步深入到更精细的粒度级别。

   >[!NOTE]
   >
   >数据表可显示的划分数量最多为 200 个。在导出划分时，该限额会有所增加。

[在Analysis Workspace中将Dimension和量度添加到您的项目](https://docs.adobe.com/content/help/zh-Hans/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html) (11:39)

[在自由形式表中使用Dimension](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table.html) (15:35)

## 将归因模型应用于划分

也可以对表中的任何划分应用归因模型。此归因模型可能与父列相同或不同。例如，您可以对“营销渠道”维度上的线性订单进行分析，但同时将 U 型订单应用于渠道中的特定跟踪代码。要编辑已应用于划分的归因模型，只需将鼠标悬停在划分模型上，然后单击&#x200B;**[!UICONTROL 编辑]**：

![划分设置](assets/breakdown_settings.png)
