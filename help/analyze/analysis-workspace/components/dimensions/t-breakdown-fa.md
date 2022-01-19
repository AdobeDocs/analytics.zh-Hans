---
description: 在 Analysis Workspace 中划分维度和维度项目。
keywords: Analysis Workspace
title: 划分维度
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
feature: Workspace Basics
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: 9f0f17936de2597611728498c5ed82d36fd01d1c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 63%

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

## 将归因模型应用于划分

也可以对表中的任何划分应用归因模型。此归因模型可能与父列相同或不同。例如，您可以对“营销渠道”维度上的线性订单进行分析，但同时将 U 型订单应用于渠道中的特定跟踪代码。要编辑已应用于划分的归因模型，只需将鼠标悬停在划分模型上，然后单击&#x200B;**[!UICONTROL 编辑]**：

![划分设置](assets/breakdown_settings.png)

将归因模型应用于划分或编辑划分时的预期行为是：

* 如果您在不存在其他属性时应用归因，则该归因将应用于整个列树。

* 如果在应用归因后添加划分，则在该维度具有默认值时，它将对添加的给定划分使用默认值。 否则，它将使用父列中的划分。 某些维度具有默认分配。  例如， [!UICONTROL 时间] 维度和 [!UICONTROL 反向链接] use [!UICONTROL 同一接触]. 的 [!UICONTROL 产品] 维度使用 [!UICONTROL 最近联系]. 其他维没有默认维，将使用父列分配。

* 如果列树中已存在属性，则更改属性只会影响您正在编辑的属性。

## 视频

在 Analysis Workspace 中将维度和量度添加到项目：

>[!VIDEO](https://video.tv.adobe.com/v/30606/?quality=12)

在自由格式表中使用维度：

>[!VIDEO](https://video.tv.adobe.com/v/40179/?quality=12)

以下是一段关于按位置划分的维度细分的视频：

>[!VIDEO](https://video.tv.adobe.com/v/24033/?quality=12)
