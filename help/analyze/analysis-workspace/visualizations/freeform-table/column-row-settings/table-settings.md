---
description: 行设置因您拖入到表格中的组件而异。
title: 行设置
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
feature: Freeform Tables
role: User, Admin
exl-id: 9057e930-b4c6-439e-b82a-8ab9828de91d
source-git-commit: 6d6a7587fc4a41be1e7ad33d3ed0280b0d82d47c
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 14%

---


# 行设置


>[!BEGINSHADEBOX]

查看自由格式表中的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [行和列设置](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]

行设置因您拖入到表格中的组件而异。要访问表格行设置，请选择每个对象中的维度、筛选器、量度、时间段或划分旁边的![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 设置]**。

![自由格式表突出显示指标的“设置”图标](assets/row-settings.png)

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 按位置划分]** | 默认情况下，此设置处于禁用状态，并且划分固定在静态行项目。例如，假设您按营销渠道划分排名前3的“页面”维度项目（主页、搜索结果、结账）。 然后，您离开项目，两周后返回。再次打开项目时，排名前 3 的页面已更改，此时“主页”、“搜索结果”和“结账”页面成为排名第 4-6 的页面。默认情况下，营销渠道划分仍会显示在“主页”、“搜索结果”和“结账”下方，即使三者现在分别位于第4-6行中。 <br>相反，**按位置划分**&#x200B;始终划分排名前 3 的项目，而不管它们具体是什么。回顾示例，当您重新打开项目时，营销渠道划分会绑定到表中排名前3的页面。 而不是主页、搜索结果和结帐，三者现在位于第4-6行中。 |
| **[!UICONTROL 百分比]** | **按列**&#x200B;计算百分比（默认）：单元格中显示的百分比是根据列总数计算的。 <br>**按行计算百分比**：单元格中的百分比是跨行计算的，而不是沿列向下计算，该计算方式以总计作为分母。 此计算对于显示百分比趋势非常有用。 |
| **[!UICONTROL 列总计]** | 这些设置仅可用于[静态行](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。<br> **显示为当前行的总和**&#x200B;显示表中行的客户端总和，这意味着总计&#x200B;*不会*&#x200B;删除重复的量度，如访问次数或人员。<br> **显示总计**&#x200B;显示服务器端总和，这意味着去除重复量度的总数。 |

## 更改行计数

要更改显示的行数，请执行以下步骤：

1. 单击表第一列顶部&#x200B;**[!UICONTROL 行]**&#x200B;旁边的数字。

   ![自由格式表，显示所显示行数的下拉列表。 已选择400行。](assets/change-row-count.gif)

1. 从下拉列表中，选择您希望表显示的行数。


## 上下文菜单

选择维度标题时，可以使用以下上下文菜单选项。

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 将选定内容复制到剪贴板]** | 将可视化图表中的选定内容复制到剪贴板。 |
| **[!UICONTROL 以CSV格式下载项目（*维度名称*）]** | 立即将可视化的维度项目（最多50,000个）下载到您的本地设备。 所选维度的最大维度项为50,000个。 |
| **[!UICONTROL 将所选内容下载为CSV]** | 立即将可视化图表的维度项目下载到您的本地设备。 |
| **[!UICONTROL 为所有维度项目创建超链接]** | 为所有维度项目创建超链接。 查看自由格式表中维度的[超链接](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 编辑所有维度项目的超链接]** | 编辑所有维度项目的超链接。 查看自由格式表中维度的[超链接](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 删除所有维度项目的超链接]** | 删除所有维度项目的超链接。 查看自由格式表中维度的[超链接](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Delete]** | 从表中删除维度。 |
| **[!UICONTROL 可视化]** | 使用任何可用的可视化图表来可视化维度。 |
| **[!UICONTROL 仅显示选定的行]** | 在可视化图表中仅显示选定项目。 |
| **[!UICONTROL 从选定范围中创建批注]** | 打开&#x200B;**[!UICONTROL 批注详细信息]**&#x200B;以添加批注。 |


在自由格式表中选择一个或多个维度项目（第一列）或一个或多个单个单元格时，可以使用以下其他上下文菜单选项。

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 创建超链接]** | 为项目创建超链接。 查看自由格式表中维度的[超链接](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 编辑超链接]** | 编辑项目的超链接。 查看自由格式表中维度的[超链接](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 删除超链接]** | 删除项目的超链接。 查看自由格式表中维度的[超链接](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 细分]** | 划分维度项。 从&#x200B;**[!UICONTROL Dimension]**、**[!UICONTROL 指标]**、**[!UICONTROL 筛选器]**&#x200B;或&#x200B;**[!UICONTROL 日期范围]**&#x200B;的列表中进行选择。 使用&#x200B;*搜索*&#x200B;替代搜索组件。 |
| **[!UICONTROL 删除选定项]** | 删除选定的行（项目）。 |
| **[!UICONTROL 趋势选择]** | 为选定内容创建趋势折线图可视化图表。 |
| **[!UICONTROL 仅显示选定的行]** | 在可视化图表中仅显示选定的行。 |
| **[!UICONTROL 显示所有行]** | 显示可视化图表中的所有行。 |
| **[!UICONTROL 从所选内容创建筛选器]** | 打开&#x200B;**[!UICONTROL 筛选器生成器]**&#x200B;以从所选内容生成筛选器。 |
| **[!UICONTROL 从所选内容创建受众]** | 打开&#x200B;**[!UICONTROL 创建受众]**&#x200B;对话框以从所选内容构建受众。 |

选择量度列标题时，可以使用以下其他上下文菜单选项。

| 选项 | 描述 |
|---|---|
| **[!UICONTROL 从所选内容创建量度]** | 从所选指标创建新指标。 量度可以是“平均值”、“媒体”、“列最大值”、“列最小值”、“列总和”。 您还可以选择在计算指标生成器中打开以创建计算指标。 |
| **[!UICONTROL 添加时间段列]** | 添加时间段列。 提供了多个选项，其中面板的日历范围确定&#x200B;*日期范围*： <li>**[!UICONTROL 在此日期范围]**&#x200B;之前&#x200B;*的日期范围*</li><li>**[!UICONTROL 这些&#x200B;*日期范围*至此日期范围]**。</li><li>**[!UICONTROL 自定义日期范围到此日期范围]**。 打开&#x200B;**[!UICONTROL 日期范围生成器]**&#x200B;以指定日期范围。</li>有关详细信息，请参阅[日期比较](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md)。 |
| **[!UICONTROL 比较时间段]** | 添加比较时间段列。 仅在维度不基于时间时可用。 为您提供了几个确定&#x200B;*日期范围*&#x200B;的选项： <li>**[!UICONTROL 在此日期范围]**&#x200B;之前&#x200B;*的日期范围*</li><li>**[!UICONTROL 自定义日期范围到此日期范围]**。 打开&#x200B;**[!UICONTROL 日期范围生成器]**&#x200B;以指定日期范围。</li>有关详细信息，请参阅[日期比较](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md)。 |
| **[!UICONTROL 修改归因模型]** | 修改列的归因模型。 |
| **[!UICONTROL 比较归因模型]** | 指定新的归因模型，并将其与所选列的归因模型进行比较。 将添加新列，其中包含新的归因模型量度。 此外，还添加了“百分比变化”列以进行比较。 |
| **[!UICONTROL 重置列宽]** | 将列宽重置为默认宽度。 |
| **[!UICONTROL 从选定范围中创建批注]** | 打开&#x200B;**[!UICONTROL 批注详细信息]**&#x200B;以添加批注。 |
| **[!UICONTROL 从所选内容创建筛选器]** | 打开&#x200B;**[!UICONTROL 筛选器生成器]**&#x200B;以从所选内容生成筛选器。 |
| **[!UICONTROL 从所选内容创建受众]** | 打开&#x200B;**[!UICONTROL 创建受众]**&#x200B;对话框以从所选内容构建受众。 |
