---
description: 创建基本 Report Builder 数据请求的步骤。
title: 创建数据请求
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 96%

---

# 创建 Report Builder 数据请求

{{legacy-arb}}

创建基本数据请求的步骤。

1. 在 Excel 中，单击&#x200B;**[!UICONTROL 创建]**。
1. 在[!UICONTROL 请求向导：第 1 步]窗口中，选择一个[报表包](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。
1. （可选）选择一个要应用到请求的区段。选择一个或多个区段后，它们将会移动到列表顶部。

   Report Builder 使用区段的方式与 Adobe Analytics 使用区段的方式相同。请参阅 [Analytics 分段指南](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)。
1. 选择[报表类型](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md)。
1. 指定[日期范围](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)和报表[粒度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)。
1. 单击&#x200B;**[!UICONTROL 下一步]**。
1. 在[布局 — 请求向导：第 2 步](/help/analyze/legacy-report-builder/layout/layout.md)窗口中，指定布局：

   | 元素 | 描述 |
   |---|---|
   | 引导布局 | 为布局提供行、列和指标网格，类似于标准 Excel 表。使用此布局，您可以在原始请求中添加划分请求。 |
   | 自定义布局 | 提供[!UICONTROL 引导布局]的大多数功能，但是允许您选择网格中的每个项目应该位于电子表格中的什么位置。此布局具备了早期版本的灵活性。 |

1. 在[!UICONTROL 指标]选项卡上，双击（或拖动）树中的指标，以将其添加到[!UICONTROL 指标]网格中。
1. 在[!UICONTROL 维度]选项卡上，双击（或拖动）维度，以将其添加到[!UICONTROL 行标签]网格中。

   在第 2 步中提供的[维度](https://experienceleague.adobe.com/docs/analytics/analyze/legacy-report-builder/layout/filter-dimenson/filter-dimensions.html)取决于您在第 1 步中选择的基本报表和报表包的配置。维度是具有关联、子关系的项目，或者是在[!UICONTROL 请求向导: 第 1 步]窗口中选择的原始报表类型指标的分类。通过在第 2 步中添加多个维度，可在数据请求中创建划分。

   有关详细信息，请参阅[添加指标和Dimension](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)。
