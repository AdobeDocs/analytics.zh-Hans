---
description: 'null'
seo-description: 'null'
seo-title: 工作区限制，Analysis Workspace中已知的限制
title: Analysis Workspace中的已知限制
translation-type: tm+mt
source-git-commit: 9d6b35c7c6de6fcb49fea3b662ff8bc9044b5e29

---


# Analysis Workspace中的已知限制

下面列出了Analysis Workspace及其相关组件中的已知限制：

## 表格

* 当日期范围或指标用作表的行时，无法添加日期比较列。
* 当区段用作表的行时，将禁用从选择中创建量度。此外，不应将选择中的创建量度应用于日期对齐列。
* 划分行的条件格式不能使用自定义范围。
* 通过应用行值设置(通常与静态行项目一起使用)，在计算总计时无法在计算总计时趋势显示表总行。
* [!UICONTROL 贡献分析] 只能在 [!UICONTROL 每日] 粒度 _下运行_。It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## 可视化

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL 流]：进入/退出维度(例如 [!UICONTROL 条目页面])不能在流中使用。
* [!UICONTROL Cohount]：非整数不能用作Cohount标准。

## 面板

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## 组件&gt;区段

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). 例如，IP地址。

## “组件”&gt;“计算量度”

* 计算量度不能在某些可视化中使用。请参阅上面的“可视化”。
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). For example, [!UICONTROL IP Address].

## “组件”&gt;“日期范围”

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## “组件”&gt;“虚拟报告套件”

* 启用报告时间处理后，不支持某些组件。For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## “组件”&gt;“报告设置”

* [!UICONTROL “报告设置”] 页面上的一些设置不适用。Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## 归因 IQ

* [!UICONTROL 归因IQ中不支持指标子集]。For a full list, see the [Attribution IQ FAQ](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).