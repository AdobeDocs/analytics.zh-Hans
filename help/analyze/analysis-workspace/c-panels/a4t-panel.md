---
description: 通过 Analytics for Target (A4T) 面板，可以在 Analysis Workspace 中分析 Adobe Target 活动和体验。
title: Analytics for Target (A4T) 面板
translation-type: tm+mt
source-git-commit: 6f86a45ae745df86f1f6fc924d995437b9992484
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 78%

---


# Analytics for Target (A4T) 面板

通过 Analytics for Target (A4T) 面板，可以在 Analysis Workspace 中分析 Adobe Target 活动和体验。通过该面板，最多还可以查看 3 个成功量度的提升度和置信度。要访问 A4T 面板，请导航到已启用 A4T 组件的报表包。然后，单击最左侧的面板图标，并将 Analytics for Target 面板拖到 Analysis Workspace 项目中。

## 面板输入 {#Input}

可以使用以下输入设置配置 A4T 面板：

| 设置 | 描述 |
|---|---|
| 目标活动 | 从“Target 活动”列表中选择活动，或从左边栏拖放活动。注意：该列表中填充有过去 6 个月内至少有 1 次点击的活动。如果您在列表中未看到某个活动，则可能是因为该活动是在 6 个月前进行的。在这种情况下，仍可从左边栏添加该活动，因为左边栏的回顾时间范围最长为 18 个月。 |
| 控制体验 | 选择您的控制体验。您可以根据需要在下拉菜单中更改控制体验。 |
| 标准化量度 | 从“独特访客数”、“访问次数”或“活动展示次数”中进行选择。对于大多数分析用例，建议使用“独特访客数”量度。此量度（也称为计数方法）将作为提升计算的分母。此外，它也会在应用置信度计算之前影响数据汇总的方式。 |
| 成功量度 | 从下拉列表中最多选择 3 个标准（非计算）成功事件，或从左边栏中拖放量度。每个量度在呈现的面板中都有一个专用表格和可视化图表。 |
| 日历日期范围 | 这将根据 Adobe Target 中的活动日期范围自动填充。你可以根据需要进行更改。 |

![面板生成器](assets/a4t-panel-builder2.png)

## 面板输出 {#Output}

Analytics for Target 面板可返回丰富的数据和可视化图表，进而帮助您更好地了解 Adobe Target 活动和体验的效果。在该面板顶部，提供了一个摘要行，用于提醒您选择的面板设置。您可以随时通过单击右上方的编辑铅笔图标来编辑该面板。

对于您选择的每个成功量度，将显示一个自由格式表和一个转化率趋势图：

![已呈现](assets/a4t-rendered.png)


每个自由格式表会显示以下量度列：

| 量度 | 描述 |
|---|---|
| 标准化量度 | “独特访客数”、“访问次数”或“活动展示次数”。 |
| 成功量度 | 在生成器中选择的量度 |
| 转化率 | 成功量度/标准化量度 |
| 提升度 | 将每个体验的转化率与控制体验的转化率进行比较。注意：提升度是目标体验的“锁定量度”；不能对其划分或将其与其他维度一起使用。 |
| 提升（低） | 在95%的置信区间内，表示变体体验可能控制的最坏提升。<br>计算：(x/y ± 1.96 std_err(x，y))/(x_control/y_control ∓ 1.96 std_err(x_control，y_control))。此处， std_err(x，y)为sqrt(xx/y -(x/y)^2)，其中xx表示平方和。 |
| 提升（中） | 代表在 95% 的置信区间内，变量体验相对于控制体验所能达到的中等提升度。这是 Reports &amp; Analytics 中的“提升度”。<br>计算：(x/y)/(x_control/y_control)- 1 |
| 提升（高） | 以95%的置信区间表示变体体验对控制的最佳提升。<br>计算：请参阅提升（下）。 |
| 置信度 | t 检验（也称为 Student t 检验）将计算置信度级别，用于指示如果再次运行该检验，出现重复结果的可能性。已对量度应用了 75%/85%/95% 的固定条件格式化范围。如果需要，可以在“列”设置下自定义此格式化范围。￼注意：￼置信度是目标体验的“锁定量度”；不能对其划分或将其与其他维度一起使用。<br>计算：应用带y+y_control-2自由度的2尾t-test，以查找x/y是否等于x_control/y_control的p值。计算t得分，其中stderr为sqrt((xx/y-(x/y)^2)/y +(xx_control/y_control-(x_control/y_control)^2)/y_control)。 回报1-p，相信它们是不同的。 |

与 Analysis Workspace 中的任何其他面板一样，您可以通过添加将帮助分析 Adobe Target 活动的其他表和[可视化图表](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)来继续进行分析。您还可以在面板级别或自由格式表内应用段。 请注意，如果在自由格式表中添加它，则必须将它覆盖整个表以保留提升和置信度计算。 此时不支持列级段。

## 常见问题解答 {#FAQ}

| 问题 | 回答 |
|---|---|
| A4T 支持哪些活动类型？ | [深入了解](https://docs.adobe.com/content/help/zh-Hans/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html)支持的活动类型。 |
| 提升度和置信度计算是否支持计算量度？ | 不支持。[深入了解](https://docs.adobe.com/content/help/zh-Hans/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html)提升度和置信度量度为何不支持计算量度。但是，可以在 A4T 报表中使用这些量度以外的计算量度。 |
| 为何 Target 和 Analytics 中的独特访客数会不一样？ | [深入了解](https://docs.adobe.com/content/help/zh-Hans/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html)不同产品中独特访客数之间的差异。 |
| 当我在分析中为特定 Target 活动应用点击区段时，为何会看到返回的不相关体验？ | A4T 维度是一个列表变量，这意味着它可以同时包含多项活动（和体验）。[了解更多](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) |
| 置信度量度是否会将极端订单计入在内或对多个优惠活动应用 Bonferroni 校正？ | 不会。[深入了解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) Analytics 如何计算置信度。 |
| 提升度和置信度量度能否与其他维度或划分一起使用？ | 提升度和置信度是“目标体验”维度的“锁定量度”，因为它们需要一个控件和变量才能计算。因此，不能对这两个量度划分或将这两个量度与其他维度一起使用。 |
| 何时会重新计算提升度和置信度？ | 无论面板何时运行（或重新运行）、面板日期范围何时更改，或将段应用于面板或表，都可提升并置信度重新计算。 将区段过滤器应用于自由形式表时，必须在所有列中应用该过滤器，否则提升和置信度将无法正确更新。 目前不支持列级段。 |

有关 Analytics for Target 报表的更多信息，请参阅 [A4T 报表](https://docs.adobe.com/content/help/zh-Hans/target/using/integrate/a4t/reporting.html)
