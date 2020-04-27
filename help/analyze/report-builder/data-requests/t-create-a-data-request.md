---
description: 创建基本 Report Builder 数据请求的步骤。
title: 创建数据请求
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 创建 Report Builder 数据请求

创建基本数据请求的步骤。

1. In Excel, click **[!UICONTROL Create]**.
1. 在窗 [!UICONTROL Request Wizard: Step 1] 口中，选择报 [表包](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。
1. （可选）选择一个要应用到请求的区段。选择一个或多个区段后，它们将会移动到列表顶部。

   Report Builder 使用区段的方式与 Adobe Analytics 使用区段的方式相同。请参阅 [Analytics 分段指南](https://marketing.adobe.com/resources/help/zh_CN/analytics/segment/)。1. （可选）选择要用于分配的[发布列表](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)。
1. 选择[报表类型](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)。
1. 指定[日期范围](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)和报表[粒度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)。
1. 单击 **[!UICONTROL Next]**.
1. 在[布局 - 请求向导：第 2 步](/help/analyze/report-builder/layout/layout.md)窗口中，指定布局：

   | 元素 | 描述 |
   |---|---|
   | 引导布局 | 为布局提供行、列和量度网格，类似于标准 Excel 表。使用此布局，您可以在原始请求中添加划分请求。 |
   | 自定义布局 | Provides most of the functionality of the [!UICONTROL Pivot Layout] but lets you choose where each item in the grid should be located in the spreadsheet. 此布局具备了早期版本的灵活性。 |

1. On the [!UICONTROL Metrics] tab, double-click (or drag) metrics in the tree to add them to the [!UICONTROL Metrics] grid.
1. On the [!UICONTROL Dimensions] tab, double-click (or drag) dimensions to the [!UICONTROL Row Labels] grid.

   在第 2 步中提供的[维度](https://marketing.adobe.com/resources/help/zh_CN/reference/dimensions.html)取决于您在第 1 步中选择的基本报表和报表包的配置。The dimensions are items that correlate, sub-relate, or are a classification of the original report type metric you selected on the [!UICONTROL Request Wizard: Step 1] window. 通过在第 2 步中添加多个维度，可在数据请求中创建划分。

   请参阅[添加量度和维度](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)，以了解更多信息。
