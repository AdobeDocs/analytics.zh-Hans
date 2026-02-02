---
title: 在Report Builder中选择一个报表包
description: 了解如何在Report Builder中选择报表包。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 96e24d5d-78fb-4e5c-8513-c5fe221d0aeb
source-git-commit: 6f7de360ac24261eabb46c6cfce99449261706de
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# 选择报告包

您可以从下拉菜单中选择一个报表包，或从单元格中选择一个报表包，然后使用新的报表包自动更新数据块。

## 从单元格选择报表包

通过从单元格中选择报表包，可以轻松使用不同的报表包刷新数据块。 您可以使用从单元格中选择的报表包刷新数据块，而不是使用单独的数据块创建全新的报表。

在以下情况下，从单元格中选择报表包会很有帮助：

* 结构相似或相同的多个报表包。
* 包含自定义组件和布局的复杂数据块格式。

要从单元格中选择报表包，请首先构建一个数据块，并将多个报表包分配给数据块以外的单元格。 然后，使用单元格&#x200B;**[!UICONTROL 中的]**&#x200B;报表包面板刷新不同报表包中的数据块。

1. 创建数据块。 有关创建数据块的信息，请参阅[创建数据块](/help/analyze/report-builder/create-a-data-block.md)。

1. 选择![报表包](/help/assets/icons/DataViewSelector.svg)中的&#x200B;**[!UICONTROL DataViewSelector]**。

1. 使用数据块外部的![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)选择单元格。

1. 从&#x200B;**[!UICONTROL 选择要从单元格]**&#x200B;添加到报表包的报表包（使用拖放），添加一个或多个报表包。 或者，您也可以双击某个报表包，将该报表包添加到&#x200B;**[!UICONTROL 包含的报表包]**&#x200B;列表。

   * 您可以使用![搜索](/help/assets/icons/Search.svg) **[!UICONTROL _选择报表包_]**&#x200B;来搜索报表包。
   * 使用![MoreSmall](/help/assets/icons/MoreSmall.svg)打开上下文菜单，以便在&#x200B;**[!UICONTROL 包含的报表包]**&#x200B;列表中上下移动报表包。
   * 使用![CrossSize75](/help/assets/icons/CrossSize75.svg)从&#x200B;**[!UICONTROL 包含的报表包]**&#x200B;列表中删除报表包。

   ![从单元格中选择报表包](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以将选定的报表包应用于选定的单元格。


## 从单元格更改报表包

1. 选择工作表中的报表包单元格位置。
1. 在Report Builder中心，在&#x200B;**[!UICONTROL 快速编辑]**&#x200B;中选择&#x200B;**[!UICONTROL 单元格]**&#x200B;中的报表包链接。
1. 从&#x200B;**[!UICONTROL 报表包]**&#x200B;下拉菜单中选择一个报表包。

   ![从单元格更改报表包](assets/change-data-view-from-cell.png){zoomable="yes"}
1. 可选，选择&#x200B;**[!UICONTROL 更改时刷新数据块]**。

1. 选择&#x200B;**[!UICONTROL 应用]**。Report Builder会根据选定的报表包刷新数据块。
