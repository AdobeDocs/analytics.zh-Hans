---
description: 在 Analysis Workspace 中创建一个同类群组并运行同类群组分析报表。
keywords: Analysis Workspace
title: 运行同类群组分析报表
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 配置同类群组分析报表

在 Analysis Workspace 中创建一个同类群组并运行同类群组分析报表。

1. In Analysis Workspace, click the **[!UICONTROL Visualizations]** icon in the left rail and drag a **[!UICONTROL Cohort Table]** to the canvas.

   ![](assets/cohort-table.png)

1. 定义 **[!UICONTROL Inclusion Criteria]**、 **[!UICONTROL Return Criteria]**、 **[!UICONTROL Cohort Type]**&#x200B;和 **[!UICONTROL Settings]** （如下表中定义）。

| 元素 | 描述 |
|--- |--- |
| **[!UICONTROL Inclusion Criteria]** | 您最多可以应用 10 个包含区段和 3 个包含量度。这个量度会指定将用户置于同类群组中的量度。例如，假设包含量度是“订单”，那么只有在同类群组分析的时间范围内下达了订单的用户才会包含在初始同类群组中。<br>这些量度之间的默认运算符是 AND，但您可以将其更改为 OR。此外，您还可以为这些量度添加数字过滤。例如：“访问次数 >= 1”。</br> |
| **[!UICONTROL Return Criteria]** | 您最多可以应用 10 个回访区段和 3 个回访量度。回访量度指示用户是已维系还是流失。例如，假设回访量度是“视频查看”，那么只有在后续时间范围（即，当用户添加到同类群组后的时间期限）内查看了视频的用户才会显示为已维系。另一个符合维系要求的量度是“访问”。 |
| **[!UICONTROL Granularity]** | 由“天”、“周”、“月”、“季度”或“年”组成的时间粒度。 |
| **[!UICONTROL Type]** | **[!UICONTROL Retention]**（默认）:保留同期群可衡量您的访客群体在一段时间内回归您的财产的程度。 这是我们一直拥有的标准同类群组，该同类群组指示用户的回访和重复行为。维系率同类群组在表格中以绿色指示。<br>**[!UICONTROL Churn]**:客户流失（也称为“流失”或“流失”）同期群衡量您的访客群随着时间推移如何从您的资产中流失。 流失率 = 1 - 维系率。流失率会显示客户有多久没有回访，从而可以很好地衡量吸引力和商机。您可以使用流失率来分析和识别焦点区域：哪些同类群组区段可能会被吸引过来。A Churn Cohort is indicated by the color red in the table (similar to fallout in our **[!UICONTROL Flow]** visualization).</br> |
| **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]**:根据上一列而非“包括”列（默认）计算保留率或客户流失率。 滚动计算会更改“回访”时段的计算方法。常规计算会单独查找符合“回访”标准且包含在包含时段的用户，而不论他们是否在上一时段的同类群组中。相反，滚动计算会查找符合“回访”标准且包含在上一时段的用户。因此，滚动计算会过滤并筛分出一段时间内持续满足“回访”标准的用户。回访标准将应用于选定时段之前的每个时段。</br><br>**[!UICONTROL Latency Table]**:延迟表衡量在包含事件发生之前和之后经过的时间。 延时表非常适用于进行事件之前/之后分析。例如，如果您即将推出某个产品或某项促销活动，并且您想跟踪在推出之前的行为，并查看在推出之后的效果，延时表可并排显示推出前后的行为，以供查看直接影响。延时表中的预包含单元格是按以下方式计算的用户：在包含时段内符合“包含”标准，然后在包含时间之前的时段内符合“回访”标准。请注意，延时表和自定义维度同类群组不能一起使用。</br><br>**[!UICONTROL Custom Dimension Cohort]**:根据所选维度而不是基于时间的同期群（默认）创建同期群。 许多客户想要按时间以外的其他方式分析他们的同类群组，现在，通过新的自定义维度同类群组功能，可以灵活地根据他们所选的维度构建同类群组。在 Adobe Analytics 中使用营销渠道、促销活动、产品、页面、区域或任何其他维度，可显示维系率根据这些维度值的不同有何变化。“自定义维度队列”区段定义仅将维度项目作为包含时段的一部分应用，而不是作为返回定义的一部分应用。</br><br>选择自定义维度同类群组选项后，您可以将所需的任何维度拖放到拖放区域中。这允许您比较同一时段内的类似维度项目。例如，您可以并排比较城市、产品、促销活动等的性能。这会返回您的前 14 个维度项目。但是，您可以使用过滤器（通过悬停在拖动的维度右侧即可访问）仅显示所需的维度项目。自定义维度同类群组不能与延时表功能一起使用。</br> |

1. 通过单 **[!UICONTROL Cohort Table Settings]** 击齿轮图标调整。

| 设置 | 说明 |
| 仅显示百分比 | 删除数字值，并仅显示百分比。|
| 将百分比近似到最接近的整数 | 将百分比值近似到最接近的整数，而不是显示小数值。|
| 显示平均百分比行 | 在表顶部插入新行，然后添加每列中值的平均值。|

## 构建同类群组分析报表

1. 单击 **[!UICONTROL Build]**.

   ![步骤结果](assets/cohort-report.png)

   报表会显示下订单的访客（*`Included`* 列）以及在后续访问中回访您网站的访客。随着时间的推移，当出现访问次数减少时，该报表可帮助您查明问题并采取相应的措施。
1. （可选）根据选定的内容创建区段。

   选择单元格（连续或非连续），然后右键单击> **[!UICONTROL Create Segment From Selection]**。

1. In the [Segment Builder](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md), further edit the segment, then click **[!UICONTROL Save]**.

   The saved segment is available for use in the [!UICONTROL Segment] panel in Analysis Workspace.
1. 命名并保存同类群组项目。
1. （可选）[策划并共享](/help/analyze/analysis-workspace/curate-share/curate.md)项目组件。

   >[!NOTE]
   >
   >在组织项目之前，必须先保存项目。

