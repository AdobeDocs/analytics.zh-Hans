---
description: 'null'
seo-description: 'null'
seo-title: 数据请求-请求向导步骤1
title: 数据请求-请求向导步骤1
uuid: 717542c3-e4 aa-4e00-b0 ca-cadet219 d13
translation-type: tm+mt
source-git-commit: 1e7dc9c769a9980e7b60bd395e7c68d5e446dae3

---


# 数据请求-请求向导步骤1

在“请求向导: 第 1 步”窗体上，您可以选择报表包、报表类型、区段并配置日期。

![](assets/rw1_overview.png)

1. **[!UICONTROL 报表包：]**&#x200B;根据您的登录凭据向您提供的报表包列表。See [Select Report Suites](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).

1. **范围选择器：**&#x200B;允许您从 Excel 的单元格中选择报表包 ID。请参阅 [选择报表包](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).

1. **区段**：区段是数据的自定义子集，或者是按您创建的规则所过滤的数据。区段基于点击数、访问次数和访客数。请参阅 [Analytics 分段指南](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)，以了解有关区段的更多信息。

   例如，您可以运行“[!UICONTROL 页面报表]”，然后应用“首次访问”区段。

1. **允许发布列表覆盖**：计划报表时，您可以选择要用于分发的发布列表。Publishing lists are set up in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin tools]**. 此请求的报表包由分配给发布列表中每个收件人的报表包 ID 替换。请参阅 [允许发布列表覆盖](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C).

1. **报表类型**：指定要在数据请求中运行的基本报表。每个请求运行一个报表，并且报表可以包含一对多维度和一对多量度。报表类型的量度和维度显示在“[!UICONTROL 请求向导: 第 2 步]”界面上。请参阅[选择报告类型](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC)。

1. **日期范围**：定义请求涵盖的时间跨度。系统提供了多种类型的请求时段，如预设、固定和滚动。最大时段数是 366。您还可以选择单元格指定的日期范围，并且将日期范围保存为模板，供以后使用。See [Configuring Report Dates](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **应用粒度**：指定报表中包含的基于时间的详细信息级别。请参阅 [粒度](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB).

>[!MORE_LIKE_THIS]
>
>* [创建数据请求](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)