---
description: 在开始将项目映射到电子表格之前，请确保电子表格未处于受保护状态。如果工作表的保护方案阻止用户执行任何操作，则无法选择电子表格中的单元格。首先取消工作表保护，然后再添加单元格映射。
seo-description: 在开始将项目映射到电子表格之前，请确保电子表格未处于受保护状态。如果工作表的保护方案阻止用户执行任何操作，则无法选择电子表格中的单元格。首先取消工作表保护，然后再添加单元格映射。
seo-title: 将指标和维度映射到单元格
solution: Analytics
title: 将指标和维度映射到单元格
topic: Report Builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 将指标和维度映射到单元格

在开始将项目映射到电子表格之前，请确保电子表格未处于受保护状态。如果工作表的保护方案阻止用户执行任何操作，则无法选择电子表格中的单元格。首先取消工作表保护，然后再添加单元格映射。

要映射的区域和单元格的数目会根据选择的量度、粒度、日期范围和设置的过滤器而不同。例如，如果选择“[!UICONTROL 网站量度]”&gt;“[!UICONTROL 流量报表]”、将粒度设置为“[!UICONTROL 周]”并将日期范围设置为“[!UICONTROL 最近 2 周]”，则系统会在“[!UICONTROL 请求向导: 第 2 步]”中提示您映射 3 个单元格（使用“[!UICONTROL 自定义布局]”时）。请求将检索第 1 周的数据和第 2 周的数据，其中每个数据点值 = 页面查看次数的值。第 3 个单元格充当行标题，您可以使用“[!UICONTROL 格式选项]”对其进行配置。

如果错误地映射电子表格中有冲突的位置，Report Builder 会发出错误。

以下部分包含更多信息：

* [选择一系列单元格](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [选择单元格的技巧](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [映射时的问题](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Select a Range of Cells {#section_1E37FB46DA194FB7A1050B8833A48AC6}

在“[!UICONTROL 请求向导: 第 2 步]”上，如果对趋势请求启用“[!UICONTROL 自定义布局]”，则可以将请求映射到一系列单元格。

Click the **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

您要映射的项目旁边。

* ** All Cells in Range:** Requires you to select a group of cells for a [!UICONTROL Custom Layout] style request.

* ** First Cell of Range:** Lets you select the top-left cell of the range, and displays the [!UICONTROL Range] orientation to specify the horizontal or vertical orientation of input and output cells (column or row). 如果使用此选项，Report Builder 会为您选择单元格。

* **范围方向：**允许您将单元格范围定向为列或行。
* **选择范围的上方单元格位置：**&#x200B;显示单元格引用。

## Techniques for selecting cells {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

，并在所需的电子表格单元格范围上单击并拖动鼠标来选择数据。连续的选择区域由黑框标出。

![](assets/twenty_cells.gif)

对于单独选择的行，每行周围都具有白色的细边框。

![](assets/twoXten_cells_highlighted.gif)

要在一个请求中映射单独的行，请按住 [!UICONTROL Ctrl] 键，然后在所需的单元格上单击并拖动光标。如果请求需要 4 个区域，每个区域具有 10 个单元格，而不是 40 个单元格连在一起的一个连续区域，则需要这样做。

![](assets/map4.png)

选择单元格后，再次单击“[!UICONTROL **范围选择]”窗体中的**[!UICONTROL 范围选择器]，以返回“[!UICONTROL 请求向导: 第 2 步]”。

## Issues when mapping {#section_CC1BCF841291447EB3A994EB08F3A099}

如果错误地选择映射到已具有活动映射的单元格，您会发现在范围选择器图标旁边的文本框中不显示单元格引用。单击“[!UICONTROL 确定]”时，Report Builder 会显示错误“选定范围与另一个请求的范围相交。请修改您的选择。”

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

如果要避免显示此消息，可采用 2 种方法：

* 通过向具有请求和映射的单元格添加格式来规划报表的格式
* 测试包含映射的电子表格区域

要测试具有嵌入请求的区域，您可以：

* 启动[!UICONTROL 请求管理器]并单击表中列出的各个请求。单击请求会突出显示请求映射到的电子表格单元格。
* 选择电子表格中您要用于新映射的单元格并单击“[!UICONTROL 来自工作表]”。[!UICONTROL 请求管理器]会选择列表中具有与所选单元格相交的输出项目的请求。如果没有选择任何请求，则表示单元格可用。

* 选择电子表格中的单元格，右键单击以显示上下文菜单，然后验证“[!UICONTROL 编辑请求]”是否可用。如果可用，则表示存在与这些单元格相关联的请求。

