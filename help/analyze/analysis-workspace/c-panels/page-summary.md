---
description: 了解如何使用页面摘要面板显示选定页面的摘要信息。
title: 页面摘要面板
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 96%

---

# 页面摘要面板 {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="页面摘要"
>abstract="快速查看一些高级量度以及有关特定页面的移入和移出。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="页面摘要面板"
>abstract="快速查看一些高级量度以及有关特定页面的移入和移出。<br/><br/>**参数&#x200B;**<br/>**添加页面维度项**：打开组件边栏，找到页面维度并通过单击尖角符号展开它以查看维度项。然后，将您需要了解的特定页面拖放到生成器中。拖放维度项后，报告将会自动使用有关页面的关键信息进行填充。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中的页面摘要面板。_<br/>__![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 中没有等效面板。_

>[!ENDSHADEBOX]

**[!UICONTROL 页面摘要]**&#x200B;面板可让您浏览有关特定页面的关键统计数据。

## 使用

要使用&#x200B;**[!UICONTROL 页面摘要]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 页面摘要]**&#x200B;面板。有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。



您可以从[!UICONTROL 报告]或 [!UICONTROL Workspace] 内访问该面板。

| 访问点 | 描述 |
| --- | --- |
| [!UICONTROL 报告] | <ul><li>该面板已被放入项目中。</li><li>左侧边栏已折叠。</li><li>仅支持页面维度。</li><li>已应用默认设置，在本例中为[!UICONTROL 页面]维度中访问次数最大的页面。您可以修改此设置。</li></ul> |
| Workspace | 创建一个新项目并选择左侧边栏中的面板图标。将[!UICONTROL 页面摘要]面板拖到自由格式表上方。请注意，页面[!UICONTROL 维度项]字段留空。从下拉列表中选择一个维度项。 |

### 面板输入 {#panel-input}

可以使用以下输入设置配置[!UICONTROL 页面摘要]面板：

![页面输入摘要](assets/page-summary-input.png)

| 输入 | 描述 |
| --- | --- |
| **[!UICONTROL 页面]** | 选择您想要浏览其关键统计数据的页面维度。 |

{style="table-layout:auto"}


选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

### 面板输出 {#panel-output}

[!UICONTROL 页面摘要]面板返回一组丰富的量度数据和可视化图表，帮助您更好地了解有关特定页面的统计数据。

![页面摘要面板](assets/page-summary-output.png)

| 可视化图表 | 描述 |
| --- | --- |
| **[!UICONTROL 页面查看次数] - 当月（到目前为止）** | [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表，显示该页面当前月份的页面查看次数。 |
| **[!UICONTROL 页面查看次数] - 4 周前** | [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表，显示该页面上个月的页面查看次数。 |
| **[!UICONTROL 页面查看次数] - 52 周前** | [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表，显示该页面去年的页面查看次数。 |
| **[!UICONTROL 趋势]** | 本月、4 周前和 52 周前的页面查看次数趋势[线形图](/help/analyze/analysis-workspace/visualizations/line.md)可视化图表。 |
| **[!UICONTROL 所有页面查看次数的百分比]** | 访问该页面所有页面查看次数的百分比摘要数字。 |
| **[!UICONTROL 页面逗留时间]** | [水平条形图](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)可视化图表，显示在该页面上逗留的时间。 |
| **[!UICONTROL 单页面访问次数]** | [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，显示该页面是唯一被访问页面的页面查看次数。 |
| **[!UICONTROL 重新载入]** | [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，显示重新载入过程中维度项的出现次数。访客刷新其浏览器是触发重新载入的最常见方式。 |
| **[!UICONTROL 登录]** | [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，显示特定维度项在访问中作为第一个值被捕获的次数。 |
| **[!UICONTROL 退出]** | [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，显示特定维度项在访问中作为最后一个值被捕获的次数。 |
| **[!UICONTROL 流]** | 以选定页面为焦点的[流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)可视化图表。您可以像在任何[流量](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)可视化图表中一样进一步深入了解数据。 |

{style="table-layout:auto"}

使用![编辑](/help/assets/icons/Edit.svg)重新配置并重新生成面板。
