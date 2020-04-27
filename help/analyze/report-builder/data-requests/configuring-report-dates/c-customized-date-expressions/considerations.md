---
description: '使用自定义表达式设置日期范围时的两个重要注意事项 '
title: 自定义日期注意事项
topic: Report builder
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 自定义日期注意事项

使用自定义表达式设置日期范围时的两个重要注意事项：

* 运行报表（或刷新请求）的日期（“截止”日期）确定可获得哪些数据。
* 报表开始和结束日期的滚动影响报表涵盖的日期范围。

由于报表的时间范围和刷新报表中的请求的日期都会影响数据的可用性，因此，请确保在适当的日期运行报表，以提取所需的信息。下面的示例说明了这两个注意事项。

Assume you make a request for [!UICONTROL Page Views] using Aggregated granularity. 在北美，一周的第一天是星期日。要获取“星期日至星期六”这一时段（例如，2008 年 11 月 23 日至 11 月 29 日）的更新报表，请在星期日（11 月 30 日）运行前一周（11 月 23 日至 11 月 29 日）的报表（刷新请求）。

使用以下自定义表达式：

*开始：* cw-1w *结束：* cw-1d

An analysis of the customize expression when the inclusive [!UICONTROL End Date] for the request is 11/30:

*开始：* cw-1w

当前周的起始日期（11 月 30 日，星期日）减去 7 天 = 上周的起始日期（11 月 23 日，星期日）

*结束：* cw-1d

当前周的起始日期（11 月 30 日，星期日）减去 1 天 = 11 月 29 日，星期六

After the customized expression is mapped to the spreadsheet, refresh the request using Sunday, November 30, 2008 as the inclusive [!UICONTROL End Date] for the floating request. 数据将反映这一周的情况。

If instead you refresh the expression and specify Saturday, November 29 as the [!UICONTROL End Date] for the floating request, the data will reflect the week 11/16 to 11/22. 这是因为请求刷新操作的引用日期提前了一天。

Here are the differences when the inclusive [!UICONTROL End Date] for the request is 11/29:

*开始：* cw-1w

当前周的起始日期（11 月 23 日，星期日）减去 7 天 = 上周的起始日期（11 月 16 日，星期日）

*结束：* cw-1d

当前周的起始日期（11 月 23 日，星期日）减去 1 天 = 11 月 22 日，星期六

在欧洲和其他一些国家/地区，一周的第一天是星期一，而不是星期日。在这种情况下，您可以自定义日历以更改开始日期。（请参阅[自定义日历](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)。)
