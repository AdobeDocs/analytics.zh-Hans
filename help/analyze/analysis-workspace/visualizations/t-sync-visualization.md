---
description: 通过同步可视化图表，您可以控制与可视化图表对应的数据表或数据源。
keywords: Analysis Workspace 将可视化图表与数据源同步
title: 管理可视化图表数据源
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: b44f40467fb4bd1c2f12c0ac99e0a0aa5479f2c9
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 96%

---

# 管理可视化图表数据源 {#manage-visualization-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_datasource_lock_selection"
>title="锁定选择"
>abstract="启用此设置可将可视化图表锁定到表位置或在数据源中选择的精确项。"

通过同步可视化图表，您可以控制与可视化图表对应的数据表或数据源。

**提示：**&#x200B;您可以通过标题旁边圆点的颜色来辨别所关联的可视化图表。颜色一致表示可视化图表基于同一个数据源。

管理数据源允许您显示数据源或锁定选择。这些设置决定了当有新数据输入时，可视化图表发生更改（或不发生更改）的方式。

1. [创建项目](/help/analyze/analysis-workspace/home.md)，其中包含一个数据表和一个[可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。
1. 在数据表中，选择要与可视化图表关联的单元格（数据源）。
1. 在可视化图表中，单击标题旁边的圆点，打开&#x200B;**[!UICONTROL 数据源]**&#x200B;对话框。选择&#x200B;**[!UICONTROL 显示数据源]**&#x200B;或&#x200B;**[!UICONTROL 锁定选择]**。

   ![](assets/manage-data-source.png)

   如果将可视化图表同步到表格单元格，则可以创建新的（隐藏）表格并使用该表格对同步的可视化图表进行颜色编码。

## 数据源设置




>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [数据源设置](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


| 元素 | 描述 |
| --- | --- |
| 链接的可视化图表 | 如果有可视化图表连接到自由格式表或同类群组表，左上侧的点即会打开以列出连接的可视化图表，并出现一个“显示”复选框选项来显示/隐藏表。将光标悬停在其上方将突出显示连接的可视化图表，单击它即会转到该可视化图表。 |
| 显示数据源 | 允许您显示（启用复选框）或隐藏（禁用复选框）与可视化图表对应的数据表。 |
| 锁定选择 | 启用此设置后，可将可视化图表锁定到相应数据表中当前选择的数据。启用后，您可以选择以下两项：<ul><li>**选定位置**：如果您要将可视化图表持续锁定在相应数据表内所选择的位置上，可选择此选项。即使这些位置中的具体项目发生更改，仍继续保持可视化状态。例如，如果您要始终显示此可视化图表中前五个促销活动名称，而无论具体是哪些促销活动名称显示在前五位，就可以选择此选项。</li><li>**选定项目**：如果您要将可视化图表持续锁定在相应数据表内当前所选定的项目中，可选择此选项。即使这些项目更改了它们在表中的排名，仍继续保持可视化状态。例如，如果您要始终显示此可视化图表中某五个特定促销活动名称，而无论这些促销活动名称的排名如何，就可以选择此选项。</li></ul> |

此新架构与上一个架构的不同之处在于，Analysis Workspace 不再创建用于存储锁定选择的重复隐藏表格。现在，数据源指向用于创建可视化图表的表格。

## 示例用例

* 您可以创建一个摘要可视化图表，并将其锁定到用于创建可视化图表的表格的单元格。当您启用“显示数据源”后，它会准确地显示表中信息的来源。源数据显示为灰色：

  ![](assets/data-source2.png)>
* 您可以添加许多可视化图表，并在同一个表格的不同单元格中显示它们的来源，如下所示。此表与上述示例中的表相同，但显示来源的单元格（和量度）却不同：

  ![](assets/data-source3.png)>
* 单击左上侧的点（数据源设置），可查看是否有可视化图表连接到自由格式表或同类群组表。将光标悬停在其上方将突出显示连接的可视化图表，单击它即会转到该可视化图表。

  ![](assets/linked-visualizations.png)>
