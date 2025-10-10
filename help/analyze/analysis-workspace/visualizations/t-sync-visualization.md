---
description: 了解如何将自由格式表或数据源同步到相应的可视化图表。
keywords: Analysis Workspace 将可视化图表与数据源同步
title: 管理数据源
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 89%

---

# 管理数据源 {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="锁定选择"
>abstract="启用此设置可将可视化图表锁定到数据源中的选定位置或选定项目。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="显示表格"
>abstract="选择&#x200B;**[!UICONTROL 显示表格]**&#x200B;将会为当前可视化图表生成一个新的数据源，并将其与原始数据源分开。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="显示表格"
>abstract="选择&#x200B;**[!UICONTROL 显示表格]**，为当前可视化图表生成一个与原始数据源区分开的新数据源。"


通过同步可视化图表，您可以控制与可视化图表对应的自由格式表或数据源。


>[!TIP]
>
>您可以通过可视化标题旁边 ![StatusOrange](/help/assets/icons/StatusOrange.svg) 的颜色来辨别所关联的可视化图表。颜色一致表示可视化图表基于同一个数据源。
>

您可以显示或隐藏数据源。您还可以将选择锁定到选定的位置或选定的项目。这些设置决定了当有新数据输入时，可视化图表发生更改（或不发生更改）的方式。

![显示下一节中描述的选项的数据源选项对话框。](assets/lock-selection.png)

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

| 选项 | 描述 |
|--- |--- |
| **[!UICONTROL 数据源]** | 从下拉菜单中选择可视化图表所基于的数据源。 |
| **[!UICONTROL 链接的可视化图表]** | 列出所有链接的可视化图表。适用于数据源（自由格式表）。 |
| **[!UICONTROL 显示数据源]** | 可显示或隐藏与可视化图表对应的数据源（自由格式表）。 |
| **[!UICONTROL 锁定选择]** | 选择此选项后，可将可视化图表 ![LockClosed](/help/assets/icons/LockClosed.svg) 锁定到相应数据表中当前选择的数据。启用后，您可以选择以下两项：  <ul><li>**选定位置**：可视化图表锁定在相应数据表中选定的&#x200B;**位置**。即使当这些位置上的具体项目发生变化时（例如由于排序或过滤），这些位置仍会被可视化。例如，如果您想要在此可视化图表中始终显示数据源中列出的前五个营销活动名称，请选择此选项。无论出现哪个营销活动名称。</li> <li>**选定项目**：可视化图表锁定在相应数据表中当前选定的特定&#x200B;**项目**&#x200B;上。即使这些项目更改了它们在表中的排名，仍继续保持可视化状态。例如，如果您想要在此可视化图表中始终显示数据源中列出的五个相同的具体营销活动名称，请选择此选项。无论这些营销活动名称的排名如何。</li></ul>如果可视化图表被锁定到连接的数据表中不再可见的数据，则可以生成一个新表。选择&#x200B;**[!UICONTROL 显示表格]**&#x200B;以为当前可视化图表生成一个新的数据源，并将其与原始数据源分开。 |
