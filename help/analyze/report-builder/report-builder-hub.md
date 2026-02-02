---
title: Report Builder 中心
description: 了解Report Builder中心。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 22%

---

# Report Builder 中心


Report Builder中心是从Excel功能区栏选择![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**&#x200B;时显示在Excel工作簿中的右侧窗格。

使用 Report Builder 中心创建、更新和管理数据块。

Report Builder中心包含![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**、![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**&#x200B;和![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL 计划]**&#x200B;按钮、**[!UICONTROL 命令]**&#x200B;面板和&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板。

![Report Builder中心](assets/hub51.png){zoomable="yes"}


选择

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 创建]**&#x200B;以[创建新数据块](create-a-data-block.md)。
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL 管理]**&#x200B;以[管理现有的数据块](manage-reportbuilder.md)。
* ![日历](/help/assets/icons/Calendar.svg) **[!UICONTROL 计划]**&#x200B;至[管理计划以通过电子邮件发送工作簿](schedule-reportbuilder.md)。

## “命令”面板

使用&#x200B;**[!UICONTROL 命令]**&#x200B;面板访问与所选单元格兼容的命令或上一个操作。

| 命令 | 可用的时间… | 用途 |
|------|------------------|--------|
| ![编辑](/help/assets/icons/Edit.svg)**[!UICONTROL 编辑数据块]** | 所选一个或多个单元格仅属于一个数据块。 | 用于编辑数据块。 |
| ![刷新](/help/assets/icons/Refresh.svg) **[!UICONTROL 刷新数据块]** | 选区至少包含一个数据块。该命令仅刷新选区中的数据块。 | 用于刷新一个或多个数据块。 |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL 刷新所有数据块]** | 工作簿包含一个或多个数据块。 | 用于刷新工作簿中的所有数据块 |
| ![发送](/help/assets/icons/Send.svg) **[!UICONTROL 发送工作簿]** | 工作簿包含一个或多个数据块。 | 使用以电子邮件的形式[发送工作簿](schedule-reportbuilder.md)。 |
| ![复制](/help/assets/icons/Copy.svg) **[!UICONTROL 复制数据块]** | 所选单元格或单元格属于一个或多个数据块。 | 用于复制数据块。 |
| ![剪切](/help/assets/icons/Cut.svg) **[!UICONTROL 剪切数据块]** | 所选单元格或单元格属于一个或多个数据块。 | 设置以剪切数据块。 |
| ![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除数据块]** | 所选一个或多个单元格仅属于一个数据块。 | 用于删除数据块 |

## 快速编辑面板

在电子表格中选择一个或多个数据块时，Report Builder会显示&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板。 您可以使用&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板同时更改一个或多个数据块中的参数。

使用&#x200B;**[!UICONTROL 快速编辑]**&#x200B;分区时所做的更改将应用于所有选定的数据块。

### 报告包

数据块从选定的报表包中提取数据。 如果在一个工作簿中选择了多个数据块并且它们不从同一报表包提取数据，则&#x200B;**报表包**&#x200B;链接显示&#x200B;**[!UICONTROL _多个_]**。

当您更改报表包时，所选内容中的所有数据块都会采用新的报表包。 数据块中的组件根据ID与新的报表包匹配。 如果在数据块中未找到某个组件，则会删除该组件并将其替换为&#x200B;**[!UICONTROL 无效值]**&#x200B;或为特定组件显示![AlertRed](/help/assets/icons/AlertRed.svg)。

要更改报表包，请从&#x200B;**[!UICONTROL 报表包]**&#x200B;下拉菜单中选择新的报表包。


### 日期范围

**日期范围**&#x200B;显示所选数据块的日期范围。如果选择具有多个日期范围的多个数据块，则&#x200B;**[!UICONTROL 日期范围]**&#x200B;链接显示&#x200B;**[!UICONTROL _多个_]**。

### 区段

**区段**&#x200B;链接显示所选数据块使用的区段的摘要列表。 如果选择应用了多个区段的多个数据块，则&#x200B;**区段**&#x200B;链接显示&#x200B;**[!UICONTROL _多个_]**。

>[!MORELIKETHIS]
>
>[选择报表包](select-report-suite.md)
>[选择日期范围](select-date-range.md)
>[使用筛选器](work-with-segments.md)
>

<!--

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the Create, Manage, and Schedule buttons, the COMMANDS panel, and The QUICK EDIT panel.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Create, Manage, and Schedule buttons

Use the Create, Manage, and Schedule buttons to create new data blocks, manage existing data blocks, or schedule datablocks.

## COMMANDS panel

Use the COMMANDS panel to access commands that are compatible with the selected cells or a previous action.

### Commands

| Commands displayed      | Available when…   | Purpose          |
|------|------------------|--------|
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block |
| Refresh data block | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Used to refresh one or more data blocks |
| Refresh all data blocks | The workbook contains one or more data blocks. | Used to refresh ALL data blocks in the workbook |
| Send workbook |   |  Send a workbook on a schedule. |
| Copy data block   | The selected cell or cell range is part of one or more data blocks. | Used to copy a data block   |
| Cut data block |   | Used to cut a data block |
| Delete data block | The selected cell or cells range is part of one data block only. | Used to delete a data block |

## QUICK EDIT panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the QUICK EDIT panel. You can use the QUICK EDIT panel to change parameters in a single data block or to change parameters in multiple data blocks at the same time.

![The Quick Edit panel in Report Builder](./assets/hub2.png)

The changes made using the Quick Edit sections apply to all selected data blocks.

### Report suites

Data blocks pull data from a selected report suite. If multiple data blocks are selected in a worksheet and they don't pull data from the same report suite, the **Report Suites** link displays *Multiple*.

When you change the report suite, all data blocks in the selection adopt the new report suite. Components in the data block are matched to the new report suite based on ID, for example, matching ```evars```). If a component isn't found in a data block, a warning message is displayed and the component is removed from the data block.

To change the report suite, select a new report suite from the drop-down menu.

![The Report Builder Hub showing the report suite drop-down menu.](./assets/image16.png)

### Date range

**[!UICONTROL Date range]** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays *Multiple*. [Learn more](/help/analyze/report-builder/select-date-range.md)

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays *Multiple*. [Learn more](/help/analyze/report-builder/work-with-segments.md)

-->