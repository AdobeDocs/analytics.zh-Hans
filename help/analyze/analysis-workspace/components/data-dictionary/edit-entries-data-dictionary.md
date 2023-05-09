---
description: Analysis Workspace 中的数据词典允许用户对 Analysis Workspace 中的各种组件进行编目和跟踪，包括组件的预期用途、批准情况、重复情况等等。
title: 编辑数据词典中的条目
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: 631f84794203cb0a1154d68149c9d64d7247ecd3
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 70%

---

# 编辑数据词典中的组件条目

Analytics 管理员可以为给定的报告包编辑数据词典中的组件条目。报告包的所有用户都可以看到所做的任何更改。

要编辑数据词典中的组件：

1. 前往包含要编辑组件的 Analysis Workspace 项目。

1. 选择 Analysis Workspace 左侧栏中的&#x200B;**数据词典**&#x200B;图标。（[数据字典概述](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)中的“访问数据字典”一节中描述了访问数据词典的其他方法。）

   显示“数据词典”窗口。

   ![数据词典管理员视图](assets/data-dictionary-admin.png)

1. 确保在下拉菜单中选择了正确的报告包。默认情况下，会显示您已在使用的报告包。

1. （可选）在搜索字段中，开始键入要编辑的组件的名称。

   组件类型可通过颜色和图标进行标识。 **Dimension** ![Dimension图标](assets/dimension-icon.png) 橙色， **区段** ![区段图标](assets/segment-icon.png) 是蓝色的， **日期范围** ![日期范围图标](assets/date-range-icon.png) 是紫色的， **量度** ![“量度”图标](assets/default-metric-icon.png) 为绿色。 Adobe图标 ![Adobe图标](assets/default-calc-metric-icon.png) 指示计算量度模板或区段模板以及计算器图标 ![计算器图标](assets/calculated-metric-icon-created.png) 指示了由您组织中的Analytics管理员创建的计算量度。

{{dd-filter-criteria}}

1. （可选）选择 **排序** 图标 ![对组件排序图标](assets/component-sort-icon.png)，然后选择以下任意过滤器选项以对组件列表进行排序：

   {{components-sort-options}}

1. 从组件列表中，选择要编辑的组件。

1. 选择组件名称旁边的&#x200B;**编辑**&#x200B;图标，即![“数据词典编辑”图标](assets/data-dictionary-edit-icon.png)。

1. 编辑有关组件的以下任何信息：

   {{dd-component-information}}

1. 单击&#x200B;**保存**&#x200B;图标，即![“数据词典保存”图标](assets/data-dictionary-save-icon.png)来保存您的更改。
