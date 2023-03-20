---
description: Analysis Workspace 中的数据词典允许用户对 Analysis Workspace 中的各种组件进行编目和跟踪，包括组件的预期用途、批准情况、重复情况等等。
title: 查看数据词典
feature: Components
role: User, Admin
source-git-commit: 8edd7b1b90e2ac3137bea734e5a0f1cb8004e743
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 62%

---

# 查看数据词典中的组件信息

{{release-limited-testing}}

“数据词典”允许您查看有关组件的信息，包括组件描述、相似组件、组件经常使用的其他组件等等。

要查看数据词典中的组件信息：

1. 前往包含要查看组件的 Analysis Workspace 项目。

1. 选择 Analysis Workspace 左侧栏中的&#x200B;[!UICONTROL **数据词典**]&#x200B;图标。（[数据字典概述](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)中的“访问数据字典”一节中描述了访问数据词典的其他方法。）

   显示“数据词典”窗口。

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 确保在下拉菜单中选择了包含您要查看的组件的报告包。默认情况下，会显示您已在使用的报告包。

1. （可选）在搜索字段中，开始键入要查看组件的名称。

   组件名称旁会显示图标以指示组件类型：

   | 图标 | 含义 |
   |---------|----------|
   | ![Dimension图标](assets/dimension-icon.png) | 指示 **维度**. Dimension由Adobe提供。 无法修改现有维度，也无法创建新维度。 |
   | ![“量度”图标](assets/default-metric-icon.png) | 指示 **标准量度** （未计算）。 标准量度由Adobe提供，无法修改。 |
   | ![Adobe图标](assets/default-calc-metric-icon.png) | 指示 **计算量度模板**. 这些是由Adobe提供且无法修改的计算量度。 |
   | ![计算器图标](assets/calculated-metric-icon-created.png) | 指示 **计算量度** 由您组织中的Analytics管理员创建。 <!-- Delete all the comments... Components with this icon can be modified by an Analytics administrator. New calculated metrics can be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![“区段”图标 ](assets/segment-icon.png) | 指示 **区段**. 这些区段可以是由Adobe提供或由您组织中的Analytics管理员创建的区段。<!-- Segments that were created byComponents with this icon can be modified by an Analytics administrator, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md). New calculated metrics can also be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![日期范围图标](assets/date-range-icon.png) | 指示 **日期范围**. 这些日期范围可以是由Adobe提供或由贵组织中的Analytics管理员创建的日期范围。 <!-- Components with this icon can be modified by an Analytics administrator. New date ranges can also be created by an Analytics administrator, as described in [Create custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). --> |

{{dd-filter-criteria}}

1. 从组件列表中，选择要查看的组件。

   显示有关组件的以下信息：

   {{dd-component-information}}

1. （可选）将组件从数据词典拖入 Analysis Workspace。