---
description: 创建基本Report builder数据请求的步骤。
seo-description: 创建基本Report builder数据请求的步骤。
seo-title: Create a Report Builder data request
solution: Analytics
title: 创建数据请求
topic: Report Builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Create a Report Builder data request

创建基本数据请求的步骤。

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).
1. （可选）选择一个要应用到请求的区段。选择一个或多个区段后，它们将会移动到列表顶部。

   Report Builder 使用区段的方式与 Adobe Analytics 使用区段的方式相同。请参阅 [Analytics 分段指南](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)。1. (Optional) Select a publishing list to use for distribution.[](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C)
1. Select a [report type](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC).
1. 指定日 [期范围](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) 和报 [告粒度](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB)。
1. Click **[!UICONTROL Next]**.
1. In the [Layout - Request Wizard Step 2](../../../analyze/report-builder/layout/layout.md#concept_D66E1C2217E24E1F837AC064C61919DB) window, specify a layout:

   | 元素 | 描述 |
   |---|---|
   | 引导布局 | 为布局提供行、列和量度网格，类似于标准 Excel 表。使用此布局，您可以在原始请求中添加划分请求。 |
   | 自定义布局 | 提供“[!UICONTROL 引导布局]”的大多数功能，但是允许您选择网格中的每个项目应该位于电子表格中的什么位置。此布局具备了早期版本的灵活性。 |

1. 在[!UICONTROL 量度]选项卡上，双击（或拖动）树中的量度，以将其添加到“[!UICONTROL 量度]”网格中。
1. 在[!UICONTROL 维度]选项卡上，双击（或拖动）维度，以将其添加到“[!UICONTROL 行标签]”网格中。

   在第 2 步中提供的[维度](https://marketing.adobe.com/resources/help/en_US/reference/dimensions.html)取决于您在第 1 步中选择的基本报表和报表包的配置。维度是具有关联、子关系的项目，或者是在“[!UICONTROL 请求向导: 第 1 步]”窗口中选择的原始报表类型量度的分类。通过在第 2 步中添加多个维度，可在数据请求中创建划分。

   请参阅[添加量度和维度](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4)，以了解更多信息。