---
title: 将受事件影响的日期与以前的范围进行比较
description: 通过将事件与先前趋势进行比较，了解其影响，如实施问题或中断。
translation-type: tm+mt
source-git-commit: b8741c1e48cf4d5602e5d7d49b1132d2743a10a0

---


# 将受事件影响的日期与以前的范围进行比较

如果数据受 [到事件影响](/help/technotes/event-impacted.md)，您可以查看历史趋势以评估其影响。 此比较对于了解事件对数据的影响程度非常有用，因此您可以决定是排除数据、添加注释到报表还是忽略它。

## 创建包含事件的日期范围

创建包含事件的日期范围，以开始探索该事件的影响。

1. 导航到 **[!UICONTROL Components]** > **[!UICONTROL Date ranges]**。
2. 单击 **[!UICONTROL Add]**.
3. 选择发生事件的日期范围。 单击 **[!UICONTROL Save]**.

   ![日期范围生成器](assets/date_range_builder.png)

## 视图事件日期和类似的先前范围并排

您可以使用自由格式表可视化将事件的日期范围与相似的先前日期范围之间的任何度量进行比较。

1. 打开一个Workspace项目，然后将“天”维添加到自由格式表。 应用累积在度量（如“发生次数”）上的最近创建的日期范围。

   ![日期范围度量](assets/date_range_metric.png)

2. 右键单击日期范围，然后单击 **[!UICONTROL Add time period column]** > **[!UICONTROL Custom date range to this date range]**。
   * 要进行一周比较，请选择事件减7天的范围。 确保一周中事件与此日期范围之间的天数一致。
   * 有关按月比较，请选择上个月的事件范围。 如果要对齐一周中的天数，还可以选择事件减28天的范围。
   * 要进行年度比较，请选择去年的事件范围。
3. 当您选择所需的日期范围时，这些日期范围会添加到自由格式表中。 您可以右键单击并添加任意想要比较的日期范围。

   ![日期一致趋势](assets/date_aligned_trends.png)

## 计算事件与相似先前范围之间的百分比差异

使用自由格式表可视化比较事件的日期范围和类似的先前日期范围之间的维值。 这些步骤说明了您可以关注的每周例子。

1. 打开一个Workspace项目，然后向自由 **格式表添加非时间维** 。 例如，您可以使用“移动设备类型”维度。 应用累积在度量上的最近创建的日期范围，如“发生次数”:

   ![按受影响的日期范围划分的移动设备类型](assets/mobile_device_type.png)

2. 右键单击日期范围，然后单击 **[!UICONTROL Compare time periods]** > **[!UICONTROL Custom date range to this date range]**。 选择事件减7天的范围。 确保一周中事件与此日期范围之间的天数一致。

   ![比较时间段菜单](assets/compare_time_custom.png)

3. 将生成的“百分比更改”量度重命名为更具体的量度，如“WoW受影响的范围”。 单击信息图标，然后单击编辑铅笔以编辑度量名称。

   ![一周比一周](assets/wow_affected_range.png)

4. 重复第3步和第4步，进行逐月和逐年比较。 您可以在同一表或单独的表中执行此操作。

## 将比较日期范围并排分析为行

如果要进一步分析上述百分比更改，可将其转换为行。

1. 添加自由形式表可视化并启用表生成器。 通过此操作，您可以按所需顺序放置百分比更改量度。
2. 按 `Ctrl` 住(Windows)或 `Cmd` (Mac)并将3%的更改量度拖动到表的行中，一次一个。

   ![表生成器](assets/table_builder.png)

3. 将“所有访问”区段添加到表的列以及任何其他所需区段。

   ![表生成器区段](assets/table_builder_segments.png)

4. 单击 **[!UICONTROL Build]**. 从生成的表中，您可以视图任何所需细分的受影响范围，而不是上周、月和年。

   ![完成的表](assets/table_builder_finished.png)
