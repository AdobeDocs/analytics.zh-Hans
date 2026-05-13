---
description: 使用“摘要数字”和“摘要变化”可视化图表来显示项目中的重要数据点。
title: 概要数字和概要变化
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
TQID: https://experienceleague.adobe.com/d8sqa6xvvXnh4qJlJua3bTCHsmm7yjcVWbMabTcJdrI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: dcae653e-62c6-4cc8-84e6-ee110b848296id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 536
ht-degree: 66%

---

# 摘要数字和变化

>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的摘要编号和摘要更改可视化图表。_<br/>_对于本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本，请参阅[摘要编号和摘要更改](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change)。_

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [摘要数字和摘要变化可视化图表](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/summary-number-and-summary-change-visualizations-2021){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]

## 摘要数字 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="摘要数字"
>abstract="创建显示总计和小计的可视化图表。"

<!-- markdownlint-enable MD034 -->

使用![摘要](/help/assets/icons/123.svg)**[!UICONTROL 摘要数字]**&#x200B;可视化图表来突出显示项目中的大型重要数字。 此可视化图表使用关联的数据源并会按以下方式运行：

* 如果未选择单元格，则选择列的总数。
* 如果选择了单个单元格，则会显示该单元格的摘要。
* 如果选择了多个单元格，则会显示选定的第一个单元格。
* 如果选择该列，则会选取列中的第一个单元格值。

![摘要数字可视化图表](asses/../assets/summary-number.png)

作为可视化图表设置的一部分，可使用特定摘要数字选项。

| 选项 | 定义 |
|--- |--- |
| **[!UICONTROL 缩写值]** | 选择&#x200B;**[!UICONTROL 缩写值]**，智能地缩写数值。 选择后，输入一个数字来定义缩写量。 例如：<br/><table><tr><td>**原始值**</td><td>**缩写值**</td><td>**结果**</td></tr><tr><td>$12,011,141.25</td><td>未选定</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>选定，设置为 `0`</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> 选定，设置为 `1`</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>选定，设置为 `2`</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>选定，设置为 `3`</td><td align="right">$12.011M</td></tr></table> |
| **[!UICONTROL 值汇总方式]** | 选择显示所选数据的最大值、最小值、平均值、中间值或总和。 |

## 摘要变化 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="摘要变化"
>abstract="创建一个显示两个数字之间增量（变化）的可视化图表"

<!-- markdownlint-enable MD034 -->


使用 ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL 摘要变化]**&#x200B;可视化图表来显示两个数字之间的增量（变化）。<!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](/help/admin/tools/success-events/success-event.md) or a calculated metric's [Show Upward Trend As](/help/components/calculated-metrics/workflow/cm-build-metrics.md) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md.md) or a calculated metric's [Show Upward Trend As](/help/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.md) option.
-->

此可视化图表的行为方式如下：

* 如果未选中单元格，此可视化图表会比较列中的前两个单元格值。
* 如果选中了一个单元格，此可视化图表会显示 0，因为它将单元格值与其自身进行比较。
* 如果选择两个单元格，则第一个选定的单元格作为分子，第二个单元格作为分母。
* 如果选择了两个以上的单元格，则只考虑将前两个单元格进行比较。
* 如果选择了某个单元格范围，则会比较该范围中选定的第一个单元格和最后一个单元格。
* 如果选择该列，则会将第一个值与其自身进行比较，这显示0的更改。


![摘要变化可视化图表显示两个数字之间的增量。](assets/summary-change.png)


作为可视化图表设置的一部分，可使用特定&#x200B;**[!UICONTROL 摘要变化选项]**。

| 选项 | 定义 |
|--- |--- |
| **[!UICONTROL 显示百分比变化]** | 显示 2 个数字之间的百分比变化。 |
| **[!UICONTROL 显示原始差异]** | 显示 2 个数字之间的原始差异。 您还可以对此选项使用缩写值，并最多显示 3 个小数位。 |
| **[!UICONTROL 缩写值]** | 选择&#x200B;**[!UICONTROL 缩写值]**，智能地缩写更改的值。 选择后，输入一个数字来定义缩写量。 例如：<br/><table><tr><td>**原始值**</td><td>**缩写值**</td><td>**结果**</td></tr><tr><td>$12,011,141.25</td><td>未选定</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>选定，设置为 `0`</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> 选定，设置为 `1`</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>选定，设置为 `2`</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>选定，设置为 `3`</td><td align="right">$12.011M</td></tr></table> |

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化图表设置](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化图表上下文菜单](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
