---
description: 了解如何选择一系列单元格、选择单元格的技巧以及映射问题疑难解答。
title: 了解如何将量度和维度映射到单元格
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: User, Admin
exl-id: e63fc679-39eb-417b-9a2b-6620db63a824
TQID: https://experienceleague.adobe.com/yeU4gugMR2nSKwjo4LuX79spXIaD4UtuaTQ52bZwGrU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 676
ht-degree: 21%

---

# 将量度和维度映射到单元格

{{legacy-arb}}

在开始将项目映射到电子表格之前，请确保您的电子表格不受保护。 如果工作表的保护方案阻止任何用户操作，您将无法选择电子表格中的单元格。 首先，取消工作表保护，然后添加单元格映射。

要映射的区域和单元格数量因您选择的量度、粒度、日期范围和设置的过滤器而不同。 例如，如果选择[!UICONTROL 网站量度] > [!UICONTROL 流量报表]，设置[!UICONTROL 周]粒度并设置[!UICONTROL 最近2周]的日期范围，则系统会在[!UICONTROL 请求向导：第2]步中提示您映射三个单元格（使用[!UICONTROL 自定义布局]时）。 该请求会检索第一周的数据和第二周的数据，其中每个数据点值等于页面查看的值。 您的第三个单元格用作行标题，您可以使用[!UICONTROL 格式选项]来配置该行标题。

如果错误地映射电子表格上不兼容的位置，Report Builder会发出错误。

有关更多信息，请参阅以下部分：

* [选择单元格范围](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [选择单元格的技术](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [映射时的问题](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## 选择单元格范围 {#section_1E37FB46DA194FB7A1050B8833A48AC6}

在“[!UICONTROL 请求向导: 第 2 步]”上，如果对趋势请求启用“[!UICONTROL 自定义布局]”，则可以将请求映射到一系列单元格。

单击要映射的项目旁边的&#x200B;**[!UICONTROL 范围选择器]** ![select_cell_icon.png](assets/select_cell_icon.png)。

* **范围中的所有单元格：**&#x200B;要求您为“[!UICONTROL 自定义布局]”类型的请求选择一组单元格。
* **范围的第 1 个单元格：**&#x200B;允许您选择范围左上角的单元格，并且显示用于指定输入和输出单元格的水平或垂直方向（列或行）的“[!UICONTROL 范围方向]”。 使用此选项可让Report Builder为您选择单元格。
* **范围方向：**&#x200B;允许您指定单元格范围的方向（列或行）。
* **选择范围的上方单元格位置：**&#x200B;显示单元格引用。

## 选择单元格的技巧 {#section_760421C3D7F84D67A639174710C93B22}

您可通过以下方法来选择数据：单击&#x200B;**[!UICONTROL 范围选择]**&#x200B;图标 ![select_cell_icon.png](assets/select_cell_icon.png)

，并在所需的电子表格单元格范围上单击并拖动鼠标。 连续选区用黑色边框标出。

![](assets/twenty_cells.gif)

单独的选定行在每行的周围都有一个细白边框。

![](assets/twoXten_cells_highlighted.gif)

若要在一个请求中映射单独的行，请使用[!UICONTROL Control]键，然后单击并将光标拖动到所需的单元格上。 如果您的请求调用的是四个区域，每个区域有10个单元格，而不是一个连续区域，每个区域有40个单元格，则可以执行此操作。

![](assets/map4.png)

选择单元格后，在[!UICONTROL 范围选择]表单上再次单击&#x200B;**[!UICONTROL 范围选择器]**&#x200B;以返回[!UICONTROL 请求向导：第2]步。

## 映射问题疑难解答{#section_CC1BCF841291447EB3A994EB08F3A099}

如果错误地选择映射到已具有活动映射的单元格，则区域选取器图标旁边的文本框中不会显示任何单元格引用。 单击[!UICONTROL 确定]时，Report Builder显示错误&#x200B;*选定范围与另一个请求的范围相交。 请更改您的选择。*

* 如果仍需要使用单元格，请右键单击所需的一个或多个单元格，然后选择&#x200B;**[!UICONTROL 删除请求]**。

如果要避免显示此消息，可以采用两种方法：

* 通过向具有请求和映射的单元格添加格式来规划报表的格式
* 测试包含映射的电子表格区域

要测试包含嵌入请求的区域，您可以：

* 启动[!UICONTROL 请求管理器]，然后单击表中列出的各个请求。 单击请求会突出显示从中映射请求的电子表格的单元格。
* 在电子表格中选择要用于新映射的单元格，然后单击[!UICONTROL 从工作表]。 [!UICONTROL 请求管理器]在列表中选择请求，该请求具有与选定单元格相交的输出项。 如果未选择请求，则单元格可用。
* 选择电子表格中的单元格，右键单击上下文菜单并验证[!UICONTROL 编辑请求]是否可用。 如果存在，则存在与这些单元格关联的请求。
