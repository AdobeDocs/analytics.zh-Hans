---
description: Adobe Analysis Workspace 及其相关组件中的已知限制列表
title: Analysis Workspace 中的已知限制
translation-type: tm+mt
source-git-commit: 06d2e64fc72c911828f089de5c487117251e060e

---


# Analysis Workspace 中的已知限制

以下是 Analysis Workspace 及其相关组件中的已知限制列表：

## 表格

* 将日期范围或量度用作表的行时，无法添加日期比较列。
* 当区段用作表的行时，将禁用通过所选内容创建量度。此外，通过所选内容创建量度不应应用于日期对齐列。
* 划分行的条件格式不能使用自定义范围。
* 当应用通过汇总行值设置来计算总数时（通常与静态行项目一起使用），表总行数不能趋势化。
* [!UICONTROL Contribution Analysis] 只能以粒度 [!UICONTROL daily] 运 _行_。 It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## 可视化图表

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]:进入／退出维度，例如, [!UICONTROL Entry page]cannot used in Flow.
* [!UICONTROL Cohort]:非整数不能用作同期群标准。

## 面板

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## “组件”>“区段”

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). 例如，IP 地址。

## “组件”>“计算量度”

* 计算量度不能用于某些可视化图表。请参阅上面的“可视化”。
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). 例如：[!UICONTROL IP Address]。

## “组件”>“日期范围”

* 自定义日期范围不 [!UICONTROL This day last year]支持 [!UICONTROL This day last month]等。

## “组件”>“虚拟报表包”

* 启用报表时间处理后，某些组件将不受支持。有关完整列表，请参阅[报表时间处理](/help/components/vrs/vrs-report-time-processing.md)。

## “组件”>“报表设置”

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace只使用底 [!UICONTROL Language/Currency/Encoding] 部的设置： [!UICONTROL Thousands separator]、 [!UICONTROL Scheduled Report Encoding]和 [!UICONTROL CSV Separator Character]。

## 归因 IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. 有关完整列表，请参阅[归因 IQ 常见问题解答](c-panels/attribution/attribution-faq.md)。
