---
description: Analysis Workspace 中的数据词典允许用户对 Analysis Workspace 中的各种组件进行编目和跟踪，包括组件的预期用途、批准情况、重复情况等等。
title: 编辑数据词典中的条目
feature: Components
role: Admin
source-git-commit: 7e105b4cd22187411dedd663080703e6daec91f5
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 编辑数据词典中的组件条目

{{release-limited-testing}}

Analytics 管理员可以为给定的报告包编辑数据词典中的组件条目。报告包的所有用户都可以看到所做的任何更改。

要编辑数据词典中的组件：

1. 前往包含要编辑组件的 Analysis Workspace 项目。

1. 选择 Analysis Workspace 左侧栏中的&#x200B;**数据词典**&#x200B;图标。（[数据字典概述](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)中的“访问数据字典”一节中描述了访问数据词典的其他方法。）

   显示“数据词典”窗口。

   ![数据词典管理员视图](assets/data-dictionary-admin.png)

1. 确保在下拉菜单中选择了正确的报告包。默认情况下，会显示您已在使用的报告包。

1. （可选）在搜索字段中，开始键入要编辑的组件的名称。

   组件名称旁会显示图标以指示组件类型：

   | 图标 | 含义 |
   |---------|----------|
   | ![Dimension图标](assets/dimension-icon.png) | 指示 **维度**. Dimension由Adobe提供。 无法修改现有维度，也无法创建新维度。 |
   | ![“量度”图标](assets/default-metric-icon.png) | 指示 **标准量度** （未计算）。 标准量度由Adobe提供，无法修改。 |
   | ![Adobe图标](assets/default-calc-metric-icon.png) | 指示 **计算量度模板** 或 **区段模板**. 这些组件由Adobe提供，无法修改。 |
   | ![计算器图标](assets/calculated-metric-icon-created.png) | 指示 **计算量度** 由您组织中的Analytics管理员创建。 |
   | ![“区段”图标 ](assets/segment-icon.png) | 指示 **区段**. 这些区段可以是由Adobe提供或由您组织中的Analytics管理员创建的区段。 |
   | ![日期范围图标](assets/date-range-icon.png) | 指示 **日期范围**. 这些日期范围可以是由Adobe提供或由贵组织中的Analytics管理员创建的日期范围。 |

{{dd-filter-criteria}}

1. 从组件列表中，选择要编辑的组件。

1. 选择组件名称旁边的&#x200B;**编辑**&#x200B;图标，即![“数据词典编辑”图标](assets/data-dictionary-edit-icon.png)。

1. 编辑有关组件的以下任何信息：

   {{dd-component-information}}

1. 单击&#x200B;**保存**&#x200B;图标，即![“数据词典保存”图标](assets/data-dictionary-save-icon.png)来保存您的更改。
