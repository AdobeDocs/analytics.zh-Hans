---
description: Analytics目标(A4T)面板让您能够分析Adobe Target活动和Analysis Workspace体验。
title: Analytics目标(A4T)小组
translation-type: tm+mt
source-git-commit: fe6202288cfc07575db437f7d0c055f1b40ddcf6
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 14%

---


# Analytics目标(A4T)小组

通过 Analytics for Target (A4T) 面板，可以在 Analysis Workspace 中分析 Adobe Target 活动和体验。它还使您能够看到3个成功指标的提升和信心。 要访问A4T面板，请导航到启用了A4T组件的报表包。 然后，单击最左侧的面板图标，将“Analytics目标”面板拖动到您的Analysis Workspace项目中。

## 面板输入 {#Input}

可以使用以下输入设置配置A4T面板：

| 设置 | 描述 |
|---|---|
| 目标活动 | 从列表目标活动中进行选择，或从左边栏拖放活动。<br>**注意：**该列表有过去6个月中至少有1次击中的活动。 如果您在列表中未看到活动，则可能比6个月大。 它仍可从左边栏添加，后者的回顾期最长为18个月。 |
| 主控体验 | 选择您的控制体验。 您可以在下拉菜单中根据需要更改它。 |
| 标准化量度 | 从“唯一访客”、“访问”或“活动印象”中进行选择。 对于大多数分析用例，建议使用唯一访客。 此度量（也称为计数方法）成为提升计算的分母。 此外，它也会在应用置信度计算之前影响数据汇总的方式。 |
| 成功量度 | 从下拉菜单中选择最多3个标准（非计算）成功事件，或从左边栏中拖放度量。 每个度量在呈现的面板中都有一个专用表格和可视化。 |
| 日历日期范围 | 这将根据活动日期范围自动填充Adobe Target。 如有必要，您可以更改它。 |

![面板构建器](assets/a4t-panel-builder2.png)

## 面板输出 {#Output}

“Analytics目标面板”返回一组丰富的数据和可视化信息，帮助您更好地了解Adobe Target活动和体验的效果。 面板顶部会提供一个摘要线，提醒您选择的面板设置。 您可以随时通过单击右上方的编辑铅笔来编辑面板。

对于您选择的每个成功量度，将显示一个自由形式表和一个转化率趋势：

![已渲染](assets/a4t-rendered.png)


每个自由形式表都显示以下度量列：

| 量度 | 描述 |
|---|---|
| 标准化指标 | 唯一访客、访问或活动印象。 |
| 成功量度 | 生成器中选择的度量 |
| 转化率 | 成功量度／标准化量度 |
| 提升度 | 将每个体验的转化率与控制体验的转化率进行比较。<br>**注意：**提升是目标体验的“锁定指标”; 不能将其分解或与其他维一起使用。 |
| 提升（低） | 代表变量体验相对于控制体验所能达到的最低提升度。 |
| 提升（中） | 代表在 95% 的置信区间内，变量体验相对于控制体验所能达到的中等提升度。这是Reports &amp; Analytics的“提升”。 |
| 提升（高） | 代表变量体验相对于控制体验所能达到的最高提升度。 |
| 置信度 | 学生T-test会计算置信度，这表示如果再次运行测试，结果复制的可能性。 对度量应用了75%/85%/95%的固定条件格式设置范围。 如果需要，可以在“列”设置下自定义此格式。 <br>**注意：**信心是目标体验的“锁定指标”; 不能将其分解或与其他维一起使用。 |

与Analysis Workspace中的任何面板一样，您可以通过添加其他表和可视化来继 [续分析](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) ，这些表和可视化可以帮助您分析Adobe Target活动。

## 常见问题解答 {#FAQ}

| 问题 | 回答 |
|---|---|
| A4T支持哪些活动类型？ | [进一步了解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) 支持哪些活动类型。 |
| 提升和置信度计算是否支持计算指标？ | 不可以。[进一步了解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) “提升和信心”中为何不支持计算量度。 但是，在这些度量之外的A4T报告中可以使用计算的度量。 |
| 为什么独特的访客会因目标和Analytics而异？ | [进一步了解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) ，产品之间的独特访客差异。 |
| 在我的分析中为特定目标活动应用点击区段时，为何会看到返回的不相关体验？ | A4T维是一个列表变量，这意味着它可以同时包含许多活动（和体验）。 [了解更多](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) |
| 置信度指标是否适用于极端订单或对多个优惠应用Bonferroni校正？ | 不可以。[进一步了解](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) Analytics如何计算信心。 |

有关Analytics目标报告的更多信息，请 [访问A4T报告](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)
