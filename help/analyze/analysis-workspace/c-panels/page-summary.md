---
description: 页面摘要面板显示所选页面的摘要信息。
title: ”页面摘要“面板
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 2aaa8c0d13755b40ec701ca6342ab773103a0422
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 28%

---

# ”页面摘要“面板 {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="页面摘要"
>abstract="快速查看一些高级量度以及有关特定页面的移入和移出。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="”页面摘要“面板"
>abstract="快速查看一些高级量度以及有关特定页面的移入和移出。<br/><br/>**参数&#x200B;**<br/>**添加页面维度项**：打开组件边栏，找到页面维度并通过单击尖角符号展开它以查看维度项。然后，将您需要了解的特定页面拖放到生成器中。拖放维度项后，报告将会自动使用有关页面的关键信息进行填充。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文在_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中记录页面摘要面板。_<br/>_在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中没有等效面板。_

>[!ENDSHADEBOX]

通过&#x200B;**[!UICONTROL 页面摘要]**&#x200B;面板，可浏览有关特定页面的关键统计信息。

## 使用

要使用&#x200B;**[!UICONTROL 页面摘要]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 页面摘要]**&#x200B;面板。 有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。



您可以从[!UICONTROL 报表]或[!UICONTROL Workspace]中访问面板。

| 接入点 | 描述 |
| --- | --- |
| [!UICONTROL 报告] | <ul><li>该面板已放入项目中。</li><li>左侧边栏折叠。</li><li>仅支持页面维度。</li><li>已应用默认设置，在本例中，为[!UICONTROL 页面]维度的访问次数最多的页面。 您可以修改此设置。</li></ul> |
| 工作区 | 创建新项目并选择左边栏中的面板图标。 将[!UICONTROL 页面摘要]面板拖动到自由格式表的上方。 请注意，页面[!UICONTROL Dimension项目]字段留空。 从下拉列表中选择一个维度项。 |

### 面板输入 {#panel-input}

您可以使用以下输入设置配置[!UICONTROL 页面摘要]面板：

![页面输入摘要](assets/page-summary-input.png)

| 输入 | 描述 |
| --- | --- |
| **[!UICONTROL 页面]** | 选择要浏览其关键统计信息的页的页维。 |

{style="table-layout:auto"}


选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

### 面板输出 {#panel-output}

[!UICONTROL 页面摘要]面板会返回一组丰富的量度数据和可视化图表，以帮助您更好地了解有关特定页面的统计信息。

![页面摘要面板](assets/page-summary-output.png)

| 可视化图表 | 描述 |
| --- | --- |
| **[!UICONTROL 页面查看次数] — 当前月份（到目前为止）** | 一个[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表，它显示当月此页面的页面查看次数。 |
| **[!UICONTROL 页面查看次数] - 4周前** | 一个[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表，它显示此页面在上个月的页面查看次数。 |
| **[!UICONTROL 页面查看次数] - 52周前** | 显示去年此页面的页面查看次数的[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表。 |
| **[!UICONTROL 趋势]** | 本月、4周前和52周前的页面查看次数的趋势[折线图](/help/analyze/analysis-workspace/visualizations/line.md)可视化图表。 |
| **[!UICONTROL 所有页面查看的百分比]** | 访问此页的所有页面查看次数的百分比的概要数字。 |
| **[!UICONTROL 页面逗留时间]** | 一个[水平条形图](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)可视化图表，它显示在此页面上花费的时间。 |
| **[!UICONTROL 单页面访问量]** | 一个[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，它显示该页面是唯一访问的页面的页面查看次数。 |
| **[!UICONTROL 重新载入]** | 一个[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，它显示重新加载期间维度项存在的次数。 访客刷新其浏览器是触发重新载入的最常见方式。 |
| **[!UICONTROL 登录]** | 一个[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，它显示给定维度项目在访问中被捕获为第一个值的次数。 |
| **[!UICONTROL 退出]** | 一个[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，它显示给定维度项目在访问中被捕获为最后一个值的次数。 |
| **[!UICONTROL 流]** | 以选定页面为焦点的[流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)可视化图表。 您可以像在任何[流量](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)可视化图表中一样进一步钻取数据。 |

{style="table-layout:auto"}

使用![编辑](/help/assets/icons/Edit.svg)重新配置并重新构建面板。
