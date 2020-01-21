---
title: 自由格式表
description: 了解自由形式表和自由形式表生成器
translation-type: tm+mt
source-git-commit: ce06a5ca2caeb266c729947c76e93c611502e6d9

---


# 自由格式表

在Analysis Workspace中，自由格式表不仅是数据表，而且是交互式可视化。 可以将组件组合拖放 [到行](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) 和列中，以创建自定义表供您分析。 每个组件都会丢弃，表格会立即更新，这样您便可以进行快速分析。

可以通过多种方式自定义表：

* **行**
   * 在分页之前，每个维度行最多可显示400行。 您可以通过调整项目的视图密度将更多行放入单个 [屏幕中](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)。
   * 行可以由其他组件划分。 要同时划分多行，只需选择多行，然后将下一个组件拖动到选定行上。 进一步了 [解细分](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html)。
   * 可以过滤 [行](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) ，以显示缩减的项集。 “行设置”下提供了其 [他设置](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html)。

* **列**
   * 可以将组件堆放在列中以创建分段指标、跨标签分析等。
   * 可在列设置下调整每列的 [视图](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)。
   * 可通过右键单击菜 [单执行多个操作](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)。 菜单根据您单击表标题、行或列的情况提供不同的操作。

## 自由格式表构建器

如果您希望先向表中添加多个组件，然后渲染数据，则可以启用自由格式表生成器。 启用该构建器后，您可以拖放到许多维度、细分、指标和区段中，以构建可解答更复杂问题的表。 数据不会实时更新，单击“构建”后，数据将会更 **[!UICONTROL 新]**。

如果您有复杂的数据问题，并且您想要构建表来回答您的问题，则Table Builder是一个省时的选项。 表生成器的其他优势包括：

* 以您需要的确切格式排列表，无需等待每个操作的呈现。
* 快速执行多达4个级别的划分。
* 为每个表行和维列定义行和细分设置。
* **[!UICONTROL 默认情况下]**，按位置划分表的各个级别(在传统的自由格式表中，默认为按项**[!UICONTROL &#x200B;目划分]**)。
* 手动对表中的静态行排序。 例如，如果希望度量行按特定顺序显示。
* 在呈现真实数据之前预览表格格式。

在此观看“自由格式表格生成器”的实 [际操作](https://youtu.be/GUMWiJAmMGI)。

## 导出自由格式表数据

自由格式表中的数据可以通过以下几种方式从Analysis Workspace中复制出来：

* 右键单击表标题，然后选择“复 **[!UICONTROL 制到剪贴板”]**。 这将导出完整（可见）表。
* 高亮显示表中的特定单元格，右键单击并选择“复 **[!UICONTROL 制到剪贴板]**”，或使用Ctrl + c热键。
* **[!UICONTROL “项目”>“下载CSV]**”。 此操作会将项目中的所有可见表导出为CSV。
