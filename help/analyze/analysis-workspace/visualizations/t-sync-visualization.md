---
description: 了解如何将可视化图表链接到自由格式表数据源。
keywords: Analysis Workspace；将可视化图表与数据源同步
title: 在Analysis Workspace中管理可视化图表数据源
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
TQID: https://experienceleague.adobe.com/ZteQfWHbl29KbcI-OUvvjEXgKytSIuR8l5R40zWQ-Rk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 19e31fec475abe3805e2637949dc86171123c210
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 18%
---
# 管理数据源 {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="锁定选择"
>abstract="启用此设置可将可视化图表锁定到数据源中的选定位置或选定项目。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="显示表格"
>abstract="选择&#x200B;**[!UICONTROL 显示表]**&#x200B;将为当前可视化图表生成新的数据源，该数据源与原始数据源不同。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="显示表格"
>abstract="选择&#x200B;**[!UICONTROL 显示表格]**，为当前可视化图表生成一个与原始数据源区分开的新数据源。"

Analysis Workspace中的每个可视化图表都基于数据源，通常是自由格式表。 通过同步可视化图表，您可以控制与可视化图表对应的自由格式表或数据源，以及可视化图表是否仍锁定到该表中的特定行。

>[!TIP]
>
>您可以通过可视化标题旁边 ![StatusOrange](/help/assets/icons/StatusOrange.svg) 的颜色来辨别所关联的可视化图表。 颜色一致表示可视化图表基于同一个数据源。
>

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/328029?captions=chi_hans&quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

## 配置数据源设置 {#configure}

1. 在Analysis Workspace中，转到要配置其数据源或锁定设置的可视化图表。

1. 将鼠标悬停在可视化图表上，然后选择&#x200B;**[!UICONTROL 设置]**&#x200B;图标![设置](/help/assets/icons/Setting.svg)。

1. 选择&#x200B;**[!UICONTROL 数据源]**&#x200B;选项卡。

   ![显示数据源、链接的可视化和锁定选择设置的数据源选项卡。](assets/lock-selection.png)

1. 配置以下任意设置：

   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 数据源]** | 选择可视化图表所基于的数据源。 |
   | **[!UICONTROL 链接的可视化图表]** | 列出链接到数据源的所有可视化图表（自由格式表）。 |
   | **[!UICONTROL 显示数据源]** | 显示或隐藏与可视化图表对应的数据源（自由格式表）。 |
   | **[!UICONTROL 锁定选择]** | 将可视化锁定到数据源中当前选定的行，然后选择&#x200B;**[!UICONTROL 选定位置]**&#x200B;或&#x200B;**[!UICONTROL 选定项]**。 请参阅[锁定选择](#lock-selection)。 |

## 锁定选择 {#lock-selection}

锁定选定内容可让可视化图表专注于在其数据源中选择的行，即使表发生更改也是如此。 例如，当您对表格进行排序或过滤、更改其日期范围或应用区段时，表格会发生更改。 锁定的可视化图表在其标题旁显示![LockClosed](/help/assets/icons/LockClosed.svg)。

如果数据源中的区段、维度或量度发生更改，并且锁定的数据不再可见，请选择&#x200B;**[!UICONTROL 显示表]**&#x200B;以生成用于可视化的新数据源（独立于原始数据源）。

锁定选定内容后，请选择以下选项之一：

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 选定职位]** | 将可视化图表锁定到数据源中所选行的&#x200B;**位置**。 即使职位中的项目发生变化，这些职位也将继续可视化。 例如，选择此选项可始终显示数据源中排名前五的营销活动名称，而不管它们属于哪个营销活动。<br><br>如果锁定划分行并且这些行不再位于表中，则不会显示可视化图表。 要再次显示它，请更新表（例如，其日期范围、区段或过滤器）或更新锁定选择。 |
| **[!UICONTROL 选定项]** | 将可视化图表锁定到数据源中选择的特定&#x200B;**项**。 即使这些项目在表中的排名发生变化，它们仍会继续可视化。 例如，选择此选项可始终显示相同的五个促销活动名称，而不管它们的排名如何。 |
