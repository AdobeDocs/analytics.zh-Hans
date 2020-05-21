---
description: Adobe Analysis Workspace 及其相关组件中的已知限制列表
title: Analysis Workspace 中的已知限制
translation-type: ht
source-git-commit: 025ac334f9191b6455eea0530a2a21c01199000a

---


# Analysis Workspace 中的已知限制

以下是 Analysis Workspace 及其相关组件中的已知限制列表：

## 表格

* 将日期范围或量度用作表的行时，无法添加日期比较列。
* 当区段用作表的行时，将禁用通过所选内容创建量度。此外，通过所选内容创建量度不应应用于日期对齐列。
* 划分行的条件格式不能使用自定义范围。
* 当应用通过汇总行值设置来计算总数时（通常与静态行项目一起使用），表总行数不能趋势化。
* [!UICONTROL Contribution Analysis] _只能_&#x200B;以 [!UICONTROL daily] 粒度运行。它不能针对 [!UICONTROL hourly]、[!UICONTROL weekly] 等数据运行。

## 可视化图表

* 利用分段的可视化图表（如 [!UICONTROL Fallout]、[!UICONTROL Flow]、[!UICONTROL Cohort] 和 [!UICONTROL Histogram]）不能接受将计算量度作为输入。
* [!UICONTROL Flow]：登入/退出维度（例如 [!UICONTROL Entry page]）无法用于流量中。
* [!UICONTROL Cohort]：非整数不能用作同类群组标准。

## 面板

* 区段比较：如果在初始放置区中使用区段模板，则不会创建 [!UICONTROL Everyone Else] 区段。

## “组件”>“区段”

* 某些量度和维度不可分段，如 [!UICONTROL Occurrences]、[!UICONTROL Unique Visitors] 等。
* 如果从工作区中创建区段（而不是从 [!UICONTROL Components > Segments] 中创建），则某些组件和运算符将不可用。例如，IP 地址。

## “组件”>“计算量度”

* 计算量度不能用于某些可视化图表。请参阅上面的“可视化图表”。
* 计算量度无法在 [!UICONTROL Attribution] 面板中使用，因为计算量度本身可以包括单独的归因模型。
* 如果从工作区中创建计算量度（而不是从 [!UICONTROL Components > Segments] 中创建），则某些组件和运算符将不可用。例如：[!UICONTROL IP Address]。

## “组件”>“日期范围”

* 自定义日期范围不支持 [!UICONTROL This day last year]、[!UICONTROL This day last month] 等。

## “组件”>“虚拟报表包”

* 启用报表时间处理后，某些组件将不受支持。有关完整列表，请参阅[报表时间处理](/help/components/vrs/vrs-report-time-processing.md)。

## “组件”>“报表设置”

* [!UICONTROL Report Settings] 页面上的某些设置不适用。Analysis Workspace 仅使用底部的 [!UICONTROL Language/Currency/Encoding] 设置：[!UICONTROL Thousands separator]、[!UICONTROL Scheduled Report Encoding] 和 [!UICONTROL CSV Separator Character]。

## 归因 IQ

* [!UICONTROL Attribution IQ] 中不支持量度的子集。有关完整列表，请参阅[归因 IQ 常见问题解答](/help/analyze/analysis-workspace/c-panels/attribution/attribution-faq.md)。
