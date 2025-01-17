---
description: 页面摘要面板显示所选页面的摘要信息。
title: ”页面摘要“面板
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 33fdd685de21736964d0cbfbc479794a9154e8a3
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 8%

---

# ”页面摘要“面板 {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="页面摘要"
>abstract="快速查看一些高级量度以及特定页面的移动情况。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="”页面摘要“面板"
>abstract="快速查看一些高级量度以及特定页面的移动情况。<br/><br/>**参数&#x200B;**<br/>**添加页面维度项**：打开组件边栏，找到页面维度并单击胡萝卜将其展开以查看维度项。 然后，将要了解的特定页面拖放到生成器中。 拖放维度项目后，报表将自动填充有关页面的关键信息。"

<!-- markdownlint-enable MD034 -->


利用此面板，可轻松浏览有关特定页面的关键统计信息。

## 访问面板

您可以从[!UICONTROL 报表]或[!UICONTROL Workspace]中访问面板。

| 接入点 | 描述 |
| --- | --- |
| [!UICONTROL 报告] | <ul><li>该面板已放入项目中。</li><li>左侧边栏折叠。</li><li>仅支持页面维度。</li><li>已应用默认设置，在此例中，[!UICONTROL 页面]维度的最常访问的页面。 您可以修改此设置。</li></ul> |
| 工作区 | 创建新项目并选择左边栏中的面板图标。 将[!UICONTROL 页面摘要]面板拖动到自由格式表的上方。 请注意，页面[!UICONTROL Dimension项]字段留空。 从下拉列表中选择一个维度项。 |

## 面板输入 {#Input}

您可以使用以下输入设置配置[!UICONTROL 页面摘要]面板：

| 设置 | 描述 |
| --- | --- |
| 区段（或其他组件）放置区 | 您可以拖放区段或其他组件以进一步筛选面板结果。 |
| 页面维度项目 | 从下拉列表中，选择要浏览其关键统计信息的页面维度项。 |

{style="table-layout:auto"}

单击&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

## 面板输出 {#output}

[!UICONTROL 页面摘要]面板会返回一组丰富的量度数据和可视化图表，以帮助您更好地了解有关特定页面的统计信息。

| 量度/可视化图表 | 描述 |
| --- | --- |
| [!UICONTROL 页面查看次数] — 当前月份，到目前为止 | 当月此页面的页面查看次数。 |
| [!UICONTROL 页面查看次数] - 4周前 | 上个月查看此页面的页数。 |
| [!UICONTROL 页面查看次数] - 52周前 | 去年此页面的页面查看次数。 |
| [!UICONTROL 趋势] | 本月、4周前和52周前的趋势页面查看图表。 |
| [!UICONTROL 所有页面查看的百分比] | 访问此页的所有页面查看次数的百分比的概要数字。 |
| [!UICONTROL 页面逗留时间] | 列出此页面逗留时间的水平条形图。 |
| [!UICONTROL 单页面访问量] | 一个摘要数字，其中列出了仅访问过此页面的页面查看次数。 |
| [!UICONTROL 重新载入] | [!UICONTROL 重新载入]量度显示重新载入期间维度项目存在的次数。 访客刷新其浏览器是触发重新载入的最常见方式。 |
| [!UICONTROL 登录] | [!UICONTROL 登入次数]量度显示给定维度项目在访问中被捕获为第一个值的次数。 |
| [!UICONTROL 退出] | [!UICONTROL 退出]量度显示给定维度项目被捕获为访问中的最后一个值的次数。 |
| [!UICONTROL 流] | 以选定页面为焦点的流程图。 您可以像在任何[流程图](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)中一样进一步钻取数据。 |

{style="table-layout:auto"}

![页面摘要面板](assets/page-sum1.png)

![量度和流量](assets/page-sum2.png)
