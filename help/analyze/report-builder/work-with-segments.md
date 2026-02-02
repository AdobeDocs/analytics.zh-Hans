---
title: 在Report Builder中使用区段
description: 了解如何在Report Builder中使用区段。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 2691fde0-59c6-45a7-80a5-8e5e221adce2
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 6%

---

# 使用区段工作

您可以在创建新数据块或从&#x200B;**[!UICONTROL 命令]**&#x200B;面板中选择&#x200B;**[!UICONTROL 编辑数据块]**&#x200B;时应用区段。

## 将区段应用到数据块

要将区段应用于整个数据块，请双击一个区段，或者将区段从组件列表拖放到表的区段部分中。

## 将筛选器应用到单独的量度

要使用区段将过滤器应用于单个量度，请执行以下操作：

* 将&#x200B;**[!UICONTROL 区段]**&#x200B;中的一个或多个区段拖放到表中的某个量度上。

* 或者：

   1. 在![表](/help/assets/icons/MoreSmall.svg)窗格中为特定量度选择&#x200B;**[!UICONTROL MoreSmall]**，然后选择&#x200B;**[!UICONTROL 筛选量度]**。

      ![区段选项卡显示指标。](./assets/filter-metric.png){zoomable="yes"}

   1. 从&#x200B;**[!UICONTROL 段]**&#x200B;下拉菜单中选择一个或多个段。 区段已添加到&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表。

      已应用![区段](assets/segments-applied.png)
   1. 选择![CrossSize75](/help/assets/icons/CrossSize75.svg)以从&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表中删除区段。 或者选择&#x200B;**[!UICONTROL 全部清除]**&#x200B;以从&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表中删除所有区段。
   1. 选择&#x200B;**[!UICONTROL 应用]**。

要查看应用的筛选器，请将光标悬停在上方或者在“表”窗格中选择量度。已应用区段的量度会显示区段图标。


## 快速编辑区段

您可以使用&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板为现有数据块添加、删除或替换区段。

在电子表格中选择单元格范围时，**[!UICONTROL 快速编辑]**&#x200B;面板中的&#x200B;**[!UICONTROL 区段]**&#x200B;链接会显示该选区中数据块使用的区段的摘要列表。

要使用&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板编辑区段，请执行以下操作：

1. 从一个或多个数据块选择单元格范围。

1. 选择&#x200B;**[!UICONTROL 区段]**&#x200B;链接以启动&#x200B;**[!UICONTROL 快速编辑]****[!UICONTROL 区段]**&#x200B;面板。


### 添加或删除区段

您可以使用“添加/删除”选项添加或删除区段。

1. 在&#x200B;**[!UICONTROL 快速编辑]****[!UICONTROL 区段]**&#x200B;面板中选择&#x200B;**[!UICONTROL 添加/删除]**&#x200B;选项卡。


   1. 从&#x200B;**[!UICONTROL 段]**&#x200B;下拉菜单中选择一个或多个段。 区段已添加到&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表。
   1. 选择![CrossSize75](/help/assets/icons/CrossSize75.svg)以从&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表中删除区段。
   1. 选择&#x200B;**[!UICONTROL 应用]**。

Report Builder显示消息以确认应用的区段更改。

### 替换区段

您可以使用另一个区段替换现有区段，以更改数据的分段方式。

1. 在&#x200B;**[!UICONTROL 快速编辑]****[!UICONTROL 区段]**&#x200B;面板中选择&#x200B;**[!UICONTROL 替换]**&#x200B;选项卡。

1. 使用&#x200B;**搜索列表**&#x200B;搜索字段来查找特定区段。

1. 选择要替换的一个或多个区段。

1. 从“替换为”下拉菜单中搜索一个或多个区段，以将区段添加到&#x200B;**[!UICONTROL 替换为]**&#x200B;列表。

1. 选择&#x200B;**[!UICONTROL 应用]**。

Report Builder会更新区段列表以反映替换情况。

## 从单元格定义数据块区段

数据块可以从单元格引用区段。 多个数据块可以引用区段的同一单元格，从而允许您一次为多个数据块轻松切换区段。

要从单元格应用区段，请执行以下操作：

1. [创建新数据块](create-a-data-block.md#create-a-data-block)或编辑现有数据块。
1. 选择&#x200B;**[!UICONTROL 区段]**&#x200B;选项卡以定义区段。
1. 选择![DataViewSelector](/help/assets/icons/DataViewSelector.svg)。

   ![从单元格中选择区段](assets/select-segment-from-cell.png){zoomable="yes"}

1. 选择要数据块从中引用区段的单元格。

1. 双击以向单元格添加区段。 或者，将一个或多个区段拖放到&#x200B;**[!UICONTROL 包括的区段]**&#x200B;部分中。

1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以创建引用单元格。

1. 从&#x200B;**区段**&#x200B;选项卡，将新创建的引用单元格区段添加到数据块。

   显示Sheet1！J1(All Data)区段的![区段选项卡已添加到表中。](assets/segment-from-cell-applied.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 完成]**。

要将引用单元格作为区段应用于其他数据块，请在&#x200B;**[!UICONTROL 表]**&#x200B;选项卡的&#x200B;**[!UICONTROL 区段]**&#x200B;列表中将该单元格引用用作区段之一。

### 使用引用单元格更改数据块区段

1. 选择电子表格中的引用单元格。

1. 在&#x200B;**[!UICONTROL 快速编辑]**&#x200B;菜单的&#x200B;**[!UICONTROL 单元格]**&#x200B;的区段下选择链接。

   单元格链接中的![段显示Sheet1！J1 （所有数据）](assets/select-segment-from-cell-in-sheet.png){zoomable="yes"}

1. 从下拉菜单中选择您的区段。

1. 选择&#x200B;**[!UICONTROL 应用]**。

<!--
You can apply segments when you create a new data block or when you select the **Edit data block** option from the COMMANDS panel.

## Apply segments to a data block

To apply a segment to the entire data block, double-click a segment or drag and drop filters from the components list into the Segments section of the Table.

## Apply segments to individual metrics

To apply segments to individual metrics, drag and drop a segment onto a metric in the table. You can also click the **...** icon to the right of a metric in the Table pane and then select **[!UICONTROL Segment metric]**. To view applied segments, hover over or select a metric in the Table pane. Metrics with applied segments display a filter icon.

![Segments tab displaying metrics.](./assets/filter_by.png)

## Quick edit segments

You can use the Quick edit panel to add, remove, or replace segments for existing data blocks.

When you select a range of cells in the spreadsheet, the **[!UICONTROL Segments]** link in the Quick edit panel displays a summary list of the segments used by the data blocks in that selection.

To edit segments using the Quick edit panel

1. Select a range of cells from one or multiple data blocks.

    ![Quick Edit segment panel showing segment options for report suites, date range, and segments.](./assets/select_multiple_dbs.png)

1. Click the link underneath **[!UICONTROL Segments]** to launch the Quick edit - Filters panel.

    ![the Segments panel showing the Add Segments field and Segments Applied lists.](./assets/quick_edit_filters.png)

### Add or remove a segment

You can add or remove segments using the Add/Remove options.

1. Select the **[!UICONTROL Add/Remove]** tab in the Quick edit-segments panel.

    All segments applied to the selected data blocks are listed in the Quick Edit-segments panel. Segments applied to all data blocks in the selection are listed under the **[!UICONTROL Applied to all selected data blocks]** heading. Segments applied to some but not all data blocks are listed under the **[!UICONTROL Applied to 1 or more selected data blocks]** heading.

    When multiple segments are present in the selected data blocks, you can search for specific segments using the **[!UICONTROL Add Filter]** search field.

    ![The Add Segments field.](./assets/add_filter.png)

1. Add segments by selecting segments from the **[!UICONTROL Add segment]** drop down menu.

    The list of searchable segments includes all segments accessible to the report suites that are present in one or more of the selected data blocks as well as all the segments that are available globally in the organization.

    Adding a segment applies the segment to all data blocks in the selection.

1. To remove segments, click the delete icon **x** to the right of segments in the **[!UICONTROL Segments applied]** list.

1. Click **[!UICONTROL Apply]** to save changes and return to the hub panel.

    Report Builder displays a message to confirm the applied segment changes.

### Replace a segment

You can replace an existing segment with another segment to change how the data is segmented.

1. Select the **[!UICONTROL Replace]** tab in the Quick edit-segment panel.

    ![Select the Replace tab.](./assets/replace_filter.png)

1. Use the **[!UICONTROL Search list]** search field to locate specific segments.

1. Choose one or more segments that you want to replace.

1. Search for one or more segments in the Replace with field.

    Selecting a filter adds it to the **[!UICONTROL Replace with]**... list.

1. Click **[!UICONTROL Apply]**.

    Report Builder updates the list of segments to reflect the replacement.

### Define data block segments from cell

Data blocks can reference segments from a cell. Multiple data blocks can reference the same cell for segments, allowing you to easily switch segments for multiple data blocks at a time.

To apply segments from a cell

1. Navigate to Step 2 in either the data block creation or editing process. See [Create a Data Block](./create-a-data-block.md).
1. Click the **[!UICONTROL Segments]** tab to define filters.
1. Click **[!UICONTROL Create segment from cell]**.

    ![Create segment from cell icon.](./assets/create-filter-from-cell.png)

1. Select the cell from which you want the data blocks to reference a segment.
   
1. Add the segment choice you wish to add to the cell by either double clicking the segment, or by dragging and dropping it into the **[!UICONTROL Segments Included]** section. 
   
   Note: Only one choice may be selected for the given cell at one time.

    ![The Add segment from cell window showing the Filters included.](./assets/select-filters.png)

1. Click **[!UICONTROL Apply]** to create the reference cell.

1. From the **[!UICONTROL Segments]** tab, add the newly created reference cell segments to your data block.

    ![Segments tab showing Sheet1!J1(All Data) segment added to the table.](./assets/reference-cell-filter.png)

1. Click **[!UICONTROL Finish]**.

    Now this cell can be referenced by other data blocks in their segments. To apply the reference cell as a segment to other data blocks, simply add the cell reference to their segments from the Segments tab. 

#### Use the reference cell to change data block segments

1. Select the reference cell in your spreadsheet.

1. Click the link under **[!UICONTROL Segments from Cell]** in the Quick Edit menu.

    ![Segments from cell link showing Sheet1!J1 (All Data)](./assets/filters-from-cell-link.png)

1. Select your segment from the drop-down menu.

    ![Segments drop down menu](./assets/filter-drop-down.png)

1. Click **[!UICONTROL Apply]**.
-->