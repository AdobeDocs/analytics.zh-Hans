---
description: 通过同步可视化信息，您可以控制与可视化对应的数据表或数据源。
keywords: Analysis Workspace;Synchronize visualization with data source
title: 管理数据源
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# 管理数据源

通过同步可视化信息，您可以控制与可视化对应的数据表或数据源。

**提示：** 您可以通过标题旁边的圆点的颜色来判断哪些可视化相关。 匹配颜色意味着可视化基于相同的数据源。

通过管理数据源，可显示数据源或锁定选择。 这些设置决定了新数据传入时可视化的更改方式（或不更改）。

1. [创建项目](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)，其中包含一个数据表和一个[可视化](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。
1. 在数据表中，选择要和可视化信息关联的单元格（数据源）。
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. 选择 **[!UICONTROL Show Data Source]** 或 **[!UICONTROL Lock Selection]**。

   ![](assets/manage-data-source.png)

   将可视化同步到表单元格会创建一个新的（隐藏的）表，并将同步的可视化与该表进行颜色编码。

| 元素 | 描述 |
|--- |--- |
| 链接的可视化图表 | 如果有可视化连接到自由格式或对列表，左上侧的点即会打开以列出连接的可视化，并出现一个“显示”复选框选项来显示/隐藏表。悬停鼠标可突出显示链接的可视化，单击鼠标可转到该可视化。 |
| 显示数据源 | 允许您显示（通过启用复选框）或隐藏（通过禁用）与可视化对应的数据表。 |
| 锁定选择 | 启用此设置后，可将可视化锁定到相应数据表中当前选定的数据。 启用后，在以下选项中进行选择：  <ul><li>**选定职位**:如果希望可视化保持锁定在相应数据表中选定的位置上，请选择此选项。 即使这些位置中的特定项目发生更改，这些位置仍将继续可视化。 例如，如果您希望始终显示此可视化中前五个活动名称，则选择此选项，而无论前五个活动名称中显示哪个名称。</li> <li>**选定项目**:如果希望可视化保持锁定在相应数据表中当前选定的特定项目上，请选择此选项。 这些项目将继续可视化，即使它们在表中的项目中更改其排名。 例如，如果您希望始终在此可视化中显示相同的五个特定活动名称，无论这些活动名称在哪里排名，请选择此选项。</li></ul> |

此新架构与上一个架构的不同之处在于，Analysis Workspace 不再创建用于存储锁定选择的重复隐藏表格。现在，数据源指向您创建可视化时所用的表。

**示例用例：**

* 您可以创建摘要可视化并将其锁定到您创建时所用的表格中的单元格。 启用“显示数据源”后，它将准确显示此信息来自表中的位置。 源数据将灰显：

   ![](assets/data-source2.png)>
* 您可以添加大量可视化信息，并从同一表中的不同单元格中对它们进行源化，如下所示。 该表与上例中的表相同，但来源单元格（和度量）不同：

   ![](assets/data-source3.png)>
* 单击左上角的圆点（数据源设置），可以查看是否有可视化连接到自由形式表或同期群表。 悬停鼠标将突出显示链接的可视化，单击鼠标将转到该可视化。

   ![](assets/linked-visualizations.png)>
