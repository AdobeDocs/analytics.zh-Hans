---
description: 让管理员级别的用户能够跨组织查看和管理计划报表。
title: 计划报表队列
topic: Reports
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 计划报表队列

让管理员级别的用户能够跨组织查看和管理计划报表。

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**

计划报表管理器中的管理员级别功能包括：

* 选项可显示 [组织中的所有计划报](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) 告。
* [组织内的高级过滤功能](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) 。
* 新的“ [报告队列](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) ”选项卡，用于列表在报告服务器上排队执行的所有报告。
* 在报表队列界面上公布[计划 ID](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1)。

## Show all Scheduled Reports {#section_3F167CAAEEC24140B476CF95B7402690}

在选项卡 **[!UICONTROL Report List]** 中，除了您个人安排的 **[!UICONTROL Show All Scheduled Reports]** 组织之外，您还可以在您的组织中工作。

>[!NOTE] 列显 **[!UICONTROL Report Name]** 示正在计划的报告的名称，该列显示您 **[!UICONTROL File Name]** 在高级投放选项中设置的任何自定义文件名。 因此，如果您计划多个报告类型相同的报告，并为每个报告指定自定义名称，则“计划报告管理器”将显示多个条目，这些条目具有相同的报告名称，但文件名不同。 这是因为正在计划的后端报告是相同的，因此“报告名称”列除了自定义的文件名之外，其它所有文件名都具有相同的报告名称（如设置）。

![](assets/show_all_scheduled_reports.png)

## 高级过滤功能 {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## 报表队列 {#section_03C866115D354BB182E90BF4D52F1E0B}

通过此队列，您可以管理并潜在地删除任何正在“阻塞”队列的计划报告。 （通常，报告在4小时后超时。）

![](assets/scheduled_reports_2.png)

报告队列还允许您“跳过计划报告一次”。 Just click the blue icon in the **[!UICONTROL Manage]** column.

## 计划 ID {#section_568B70F4228C4229977CB85D2DCD53A1}

Having the **[!UICONTROL Schedule ID]** exposed in the Report Queue interface helps when you need to contact Adobe Client Care for resolution of a scheduled reports issue.

![](assets/schedule_id.png)
