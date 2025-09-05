---
description: 了解如何使用Analytics for Target面板分析您在Analysis Workspace中的Adobe Target活动和体验。
title: Analytics For Target面板
feature: Panels
role: User, Admin
exl-id: 36bca104-37b8-43c6-b8d0-b607a9a333cc
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 97%

---

# “Analytics for Target” 面板 {#analyze-for-target-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_button"
>title="Analytics for Target"
>abstract="在 Analysis Workspace 中分析 Target 的活动和体验。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_panel"
>title="“Analytics for Target” 面板"
>abstract="在 Analysis Workspace 中分析 Target 的活动和体验。<br/><br>**参数&#x200B;**<br/>**Target 活动**：分析的 Target 活动。<br/>**控制体验**：所选目标活动的控制体验。<br/>**标准化量度**：访客、访问次数或展示次数。此量度（也称为计数方法）将作为提升计算的分母。此外，它也会在应用置信度计算之前影响数据汇总的方式。<br/>**成功量度**：最多 3 个标准（非计算）成功量度来分析 Target 活动。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中的 Analytics for Target 面板。_<br/>_请参阅[试验面板](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)，了解如何比较_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 中的不同用户体验、营销或消息变化。_

>[!ENDSHADEBOX]

通过 Analytics for Target 面板，可以在 Analysis Workspace 中分析 Adobe Target 活动和体验。通过该面板，最多还可以查看 3 个成功量度的提升度和置信度。要访问 Analytics for Target 面板，请导航到启用了 Analytics for Target 组件的报告包。然后，选择最左侧的面板图标，并将 Analytics for Target 面板拖入 Analysis Workspace 项目中。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analytics for Target 面板](https://video.tv.adobe.com/v/37247?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]

## 使用

要使用 **[!UICONTROL Analytics for Target]** 面板：

1. 创建 **[!UICONTROL Analytics for Target]** 面板。有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。

### 面板输入 {#panel-nput}

您可以使用以下输入设置来配置 Analytics for Target 面板：

![A4T 面板输入](assets/a4t-panel-input.png)

| 设置 | 描述 |
|---|---|
| **[!UICONTROL 目标活动]** | 从目标活动列表中选择。该列表填充了过去 6 个月至少被点击 1 次的活动。如果您在列表中未看到某个活动，则可能是因为该活动是在 6 个月前进行的。在这种情况下，仍可从左边栏添加该活动，因为左边栏的回顾窗口最长为 18 个月。 |
| **[!UICONTROL 控制体验]** | 选择控制体验。 |
| **[!UICONTROL 标准化量度]** | 选择访客、访问次数或展示次数。对于大多数分析用例，建议使用[!UICONTROL 访客]。此量度（也称为计数方法）将作为提升计算的分母。此外，它也会在应用置信度计算之前影响数据汇总的方式。 |
| **[!UICONTROL 成功量度]** | 从下拉菜单中最多选择 3 个标准（非计算）成功量度，或从组件边栏的“量度”中拖放量度。每个量度在呈现的面板中都有一个专用表格和可视化图表。 |

选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

### 面板输出 {#panel-output}

Analytics for Target 面板可返回丰富的数据和可视化图表，进而帮助您更好地了解 Adobe Target 活动和体验的效果。在该面板顶部，提供了一个摘要行，用于提醒您选择的面板设置。对于您选择的每个成功量度，都会出现一个[自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)和一个[线形图](/help/analyze/analysis-workspace/visualizations/line.md)可视化图表来显示转化率趋势：

![已呈现](assets/a4t-panel-output.png)

每个自由格式表会显示以下量度列：

| 量度 | 描述 |
|---|---|
| **[!UICONTROL 标准化量度]** | 输入面板中选择的标准化量度：独特访客量、访问次数或活动展示次数。 |
| **[!UICONTROL 成功量度]** | 输入面板中选择的成功量度。 |
| **[!UICONTROL 转化率]** | 成功量度/标准化量度。 |
| **[!UICONTROL 提升度]** | 每个体验与对照体验比较转化率。注意：提升度是目标体验的&#x200B;*锁定量度*，不能对其细分或将其与其他维度一起使用。 |
| **[!UICONTROL 提升度（下限）]** | 这个值代表在 95% 的置信区间内，变量体验相对于控制体验所能达到的最差提升度。<br>有关更多信息，请参阅[统计计算](https://experienceleague.adobe.com/zh-hans/docs/target/using/reports/statistical-methodology/statistical-calculations)和[完整置信度计算器](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) Excel 文件。 |
| **[!UICONTROL 提升度（中等）]** | 这个值代表在 95% 的置信区间内，变量体验相对于控制体验所能达到的中等提升度。<br>有关更多信息，请参阅[统计计算](https://experienceleague.adobe.com/zh-hans/docs/target/using/reports/statistical-methodology/statistical-calculations)和[完整置信度计算器](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) Excel 文件。 |
| **[!UICONTROL 提升度（上限）]** | 这个值代表在 95% 的置信区间内，变量体验相对于控制体验所能达到的最佳提升度。<br>有关更多信息，请参阅[统计计算](https://experienceleague.adobe.com/zh-hans/docs/target/using/reports/statistical-methodology/statistical-calculations)和[完整置信度计算器](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) Excel 文件。 |
| **[!UICONTROL 置信度]** | t 检验（也称为 Student t 检验）将计算置信度级别，用于指示如果再次运行该检验，出现重复结果的可能性。已对量度应用了 75%/85%/95% 的固定条件格式化范围。如果需要，可以在“列”设置下自定义此格式化范围。注意：置信度是 Target 体验的“固定量度”；无法细分它或将它与其他维度一起使用。<br>有关更多信息，请参阅[统计计算](https://experienceleague.adobe.com/zh-hans/docs/target/using/reports/statistical-methodology/statistical-calculations)和[完整置信度计算器](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) Excel 文件。 |

与 Analysis Workspace 中的任何其他面板一样，通过添加其他帮助您分析 Adobe Target 活动的表和[可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)即可继续进行分析。还可在面板级别或自由格式表内应用区段。请注意，如果在自由格式表内添加它，则必须让它横跨整个表以保留提升和置信度计算结果。目前不支持列级区段。

使用![编辑](/help/assets/icons/Edit.svg)重新配置并重新生成面板。

## 常见问题解答 {#FAQ}

| 问题 | 回答 |
|---|---|
| Analytics for Target 支持哪些活动类型？ | [深入了解](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup)支持的活动类型。 |
| 提升度和置信度计算是否支持计算量度？ | 不支持。[深入了解](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence)提升度和置信度量度为何不支持计算量度。但是，可以在 Analytics for Target 报告中使用这些量度以外的计算量度。 |
| 为何 Target 和 Analytics 中的独特访客量会不一样？ | [了解更多](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports)有关不同产品中独特访客量之间的差异。 |
| 当我在分析中为特定 Target 活动应用点击区段时，为何会看到返回的不相关体验？ | Analytics for Target 维度是一个列表变量，这意味着它可以同时包含多项活动（和体验）。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports) |
| 置信度量度是否会将极端订单计入在内或对多个产品建议活动应用 Bonferroni 校正？ | 不会。[深入了解](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence) Analytics 如何计算置信度。 |
| 提升度和置信度量度能否与其他维度或划分一起使用？ | 提升度和置信度是“目标体验”维度的“锁定量度”，因为它们需要一个控件和变量才能计算。因此，不能对这两个量度划分或将这两个量度与其他维度一起使用。 |
| 何时会重新计算提升度和置信度？ | 只要生成面板、面板日期范围发生变化或将区段应用于面板或表，即可随时重新计算提升度和置信度。当您将区段过滤器应用于自由格式表时，必须横跨所有列应用区段，否则提升度和置信度无法正确更新。不支持列级区段。 |

有关 Analytics for Target 报告的更多信息，请访问[Analytics for Target 报告](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/a4t/reporting)
