---
description: 'null'
title: 数据请求 - 请求向导第 1 步
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 数据请求 - 请求向导第 1 步

在“请求向导: 第 1 步”窗体上，您可以选择报表包、报表类型、区段并配置日期。

![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**:根据您的登录凭据列表可用的报表包。 See [Select Report Suites](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **范围选择器：**&#x200B;允许您从 Excel 的单元格中选择报表包 ID。请参阅[选择报表包](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。

1. **区段**：区段是数据的自定义子集，或者是按您创建的规则所过滤的数据。区段基于点击数、访问次数和访客数。请参阅 [Analytics 分段指南](https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/seg-home.html)，以了解有关区段的更多信息。

   For example, you can run a [!UICONTROL Pages Report], and then apply a First Time Visits segment.

1. **允许发布列表覆盖**：计划报表时，您可以选择要用于分发的发布列表。Publishing lists are set up in **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. 此请求的报表包由分配给发布列表中每个收件人的报表包 ID 替换。请参阅[允许发布列表覆盖](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)。

1. **报表类型**：指定要在数据请求中运行的基本报表。每个请求运行一个报表，并且报表可以包含一对多维度和一对多量度。Metrics and dimensions for a report type are displayed on the [!UICONTROL Request Wizard; Step 2] interface. See [Select Report Types](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **日期范围**：定义请求涵盖的时间跨度。系统提供了多种类型的请求时段，如预设、固定和滚动。最大时段数是 366。您还可以选择单元格指定的日期范围，并且将日期范围保存为模板，供以后使用。请参阅[配置报表日期](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **应用粒度**：指定报表中包含的基于时间的详细信息级别。请参阅 [粒度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)。

>[!MORELIKETHIS]
>
>* [创建数据请求](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)

