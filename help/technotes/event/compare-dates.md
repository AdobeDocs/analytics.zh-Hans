---
title: 将受事件影响的日期与先前的范围进行比较
description: 将事件与先前的趋势进行比较，了解其影响，如实施问题或中断。
translation-type: tm+mt
source-git-commit: 74a1edadde1899c9e51019cb7e7bb120b6e04d64

---


# 将受事件影响的日期与先前的范围进行比较

如果事件影 [响了](overview.md)，您可以查看历史趋势来评估其影响。 此比较对于了解事件对数据的影响程度非常有价值，因此您可以决定是排除数据、在报告中添加备注还是忽略它。

## 创建包含事件的日期范围

创建包含事件的日期范围，以开始探索该事件的影响。

1. 导航到 **[!UICONTROL Components]** > **[!UICONTROL Date ranges]**。
2. 单击 **[!UICONTROL Add]**.
3. 选择发生事件的日期范围。 单击 **[!UICONTROL Save]**.

   ![日期范围生成器](assets/date_range_builder.png)

## 视图事件日期和类似的先前范围并排

您可以使用自由形式表可视化将事件的日期范围与相似的先前日期范围之间的任何度量进行比较。

1. 打开一个Workspace项目，并将“天”维添加到自由形式表。 应用累积在度量上的最近创建的日期范围，如“发生次数”。

   ![日期范围度量](assets/date_range_metric.png)

2. 右键单击日期范围，然后单击 **[!UICONTROL Add time period column]** > **[!UICONTROL Custom date range to this date range]**。
   * 要进行一周比较，请选择事件减7天的范围。 确保事件与此日期范围之间的一周中的天数保持一致。
   * 对于按月比较，请选择上个月事件的范围。 如果要对齐一周中的天数，还可以选择事件减28天的范围。
   * 要进行逐年比较，请选择去年的事件范围。
3. 当您选择所需的日期范围时，这些日期范围将添加到自由格式表中。 您可以右键单击并添加任意想要比较的日期范围。

   ![日期一致趋势](assets/date_aligned_trends.png)

## 计算事件与相似先验范围之间的百分比差异

使用自由形式表可视化，比较事件的日期范围和类似的先前日期范围之间的维度值。 这些步骤说明了您可以关注的一周比一周的示例。

1. 打开一个Workspace项目，并向 **自由形式表添加** 一个非时间维。 例如，您可以使用“移动设备类型”维。 应用累积在度量上的最近创建的日期范围，如“发生次数”:

   ![按受影响日期范围划分的移动设备类型](assets/mobile_device_type.png)

2. 右键单击日期范围，然后单击 **[!UICONTROL Compare time periods]** > **[!UICONTROL Custom date range to this date range]**。 选择事件减7天的范围。 确保事件与此日期范围之间的一周中的天数保持一致。

   ![比较时段菜单](assets/compare_time_custom.png)

3. 将生成的“百分比更改”量度重命名为更具体的指标，如“WoW受影响范围”。 单击信息图标，然后单击编辑铅笔以编辑度量名称。

   ![一周比一周](assets/wow_affected_range.png)

4. 重复步骤3和4，进行逐月和逐年比较。 可以在同一表或单独的表中执行此操作。

## 并排分析比较日期范围（如行）

如果要进一步分析上述百分比更改，可以将它们转换为行。

1. 添加自由形式表可视化并启用表生成器。 通过此操作，您可以按所需顺序放置百分比更改量度。
2. 按住 `Ctrl` (Windows) `Cmd` 或(Mac)并将3%的更改量度拖动到表的行中，一次一个。

   ![表生成器](assets/table_builder.png)

3. 将“所有访问”区段添加到表的列，以及任何其他所需的区段。

   ![表生成器区段](assets/table_builder_segments.png)

4. 单击 **[!UICONTROL Build]**. 从生成的表中，您可以视图任何所需区段的受影响范围与上周、月和年的相比。

   ![完成的表](assets/table_builder_finished.png)
