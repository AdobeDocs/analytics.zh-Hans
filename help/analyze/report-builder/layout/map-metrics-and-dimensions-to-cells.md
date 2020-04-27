---
description: 在开始将项目映射到电子表格之前，请确保电子表格未处于受保护状态。如果工作表的保护方案阻止用户执行任何操作，则无法选择电子表格中的单元格。首先取消工作表保护，然后再添加单元格映射。
title: 将量度和维度映射到单元格
topic: Report builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 将量度和维度映射到单元格

在开始将项目映射到电子表格之前，请确保电子表格未处于受保护状态。如果工作表的保护方案阻止用户执行任何操作，则无法选择电子表格中的单元格。首先取消工作表保护，然后再添加单元格映射。

要映射的区域和单元格的数目会根据选择的量度、粒度、日期范围和设置的过滤器而不同。例如，如果您选择 [!UICONTROL Site Metric] >、 [!UICONTROL Traffic Report]设置 [!UICONTROL Week] 粒度和设置日期范围，则系统会提示您在上映射三个单元格(使用时 [!UICONTROL Last 2 Weeks]) [!UICONTROL Custom Layout][!UICONTROL Request Wizard: Step 2]。 请求将检索第 1 周的数据和第 2 周的数据，其中每个数据点值 = 页面查看次数的值。Your third cell serves as the row heading, which you can configure using [!UICONTROL Format Options].

如果错误地映射电子表格中有冲突的位置，Report Builder 会发出错误。

以下部分包含更多信息：

* [选择单元格范围](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [选择单元格的技巧](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [映射时的问题](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## 选择单元格范围 {#section_1E37FB46DA194FB7A1050B8833A48AC6}

On the [!UICONTROL Request Wizard: Step 2], when you enable [!UICONTROL Custom Layout] for a trended request, you can map the request to a range of cells.

单击 **[!UICONTROL Range Selector]** select_ ![cell_icon.png](assets/select_cell_icon.png)

。

* **范围内的所有单元格：** 要求您为样式请求选择一组单 [!UICONTROL Custom Layout] 元格。
* **范围的第一个单元格：** 允许您选择范围的左上角的单元格，并显示方向以指 [!UICONTROL Range] 定输入和输出单元格（列或行）的水平或垂直方向。 如果使用此选项，Report Builder 会为您选择单元格。
* **范围方向：**&#x200B;允许您指定单元格范围的方向（列或行）。
* **选择范围的上方单元格位置：**&#x200B;显示单元格引用。

## 选择单元格的技巧 {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

，并在所需的电子表格单元格范围上单击并拖动鼠标。连续的选择区域由黑框标出。

![](assets/twenty_cells.gif)

对于单独选择的行，每行周围都具有白色的细边框。

![](assets/twoXten_cells_highlighted.gif)

To map separate rows in one request, use the [!UICONTROL Control] key, then click and drag the cursor over the desired cells. 如果请求需要 4 个区域，每个区域具有 10 个单元格，而不是 40 个单元格连在一起的一个连续区域，则需要这样做。

![](assets/map4.png)

选择单元格后，再次单 **[!UICONTROL Range Selector]** 击表单上 [!UICONTROL Range Selection] 的图标以返回到 [!UICONTROL Request Wizard: Step 2]。

## 映射时的问题 {#section_CC1BCF841291447EB3A994EB08F3A099}

如果错误地选择映射到已具有活动映射的单元格，您会发现在范围选择器图标旁边的文本框中不显示单元格引用。When you click [!UICONTROL OK], report builder displays the error, &quot;The range selected intersects another request&#39;s range. 请修改您的选择。”

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

如果要避免显示此消息，可采用 2 种方法：

* 通过向具有请求和映射的单元格添加格式来规划报表的格式
* 测试包含映射的电子表格区域

要测试具有嵌入请求的区域，您可以：

* Launch the [!UICONTROL Request Manager] and click on individual requests listed in the table. 单击请求会突出显示请求映射到的电子表格单元格。
* Select cells in the spreadsheet you intend to use for a new mapping and click [!UICONTROL From Sheet]. The [!UICONTROL Request Manager] selects the request in the list which has an output item that intersects the selected cell. 如果没有选择任何请求，则表示单元格可用。
* Select cells in the spreadsheet, right-click in the context menu and verify if [!UICONTROL Edit Request] is available. 如果可用，则表示存在与这些单元格相关联的请求。
