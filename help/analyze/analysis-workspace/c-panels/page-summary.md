---
description: 页面摘要面板显示所选页面的摘要信息。
title: 页面摘要面板
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: bef175d9675134f4932407a0b9e4a3c67b1d27a5
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 8%

---

# 页面摘要面板

此 [!UICONTROL 页面摘要] 面板最初是Reports &amp; Analytics中的报表，位于“报表”>“参与”>“页面分析”>“页面摘要”下。 它现在也是一个Workspace面板。 利用此面板，可轻松浏览有关特定页面的关键统计信息。

## 访问面板

您可以从中访问面板 [!UICONTROL 报告] 或范围 [!UICONTROL 工作区].

| 接入点 | 描述 |
| --- | --- |
| [!UICONTROL 报告] | <ul><li>该面板已拖放到项目中。</li><li>左侧边栏处于折叠状态。</li><li>仅支持页面维度。</li><li>已应用默认设置，在这种情况下，访问次数最多的页面[!UICONTROL 页面] 维度。 您可以修改此设置。</li></ul> |
| 工作区 | 创建新项目并选择左边栏中的面板图标。 拖动 [!UICONTROL 页面摘要] 自由格式表上方的面板。 请注意，页面 [!UICONTROL Dimension项目] 字段留空。 从下拉列表中选择一个维度项。 |

## 面板输入 {#Input}

您可以配置 [!UICONTROL 页面摘要] 面板使用这些输入设置：

| 设置 | 描述 |
| --- | --- |
| 区段（或其他组件）拖放区域 | 您可以拖放区段或其他组件以进一步筛选面板结果。 |
| 页面维度项目 | 从下拉列表中，选择要浏览其关键统计信息的页面维度项。 |

{style="table-layout:auto"}

单击 **[!UICONTROL 生成]** 以构建面板。

## 面板输出 {#output}

此 [!UICONTROL 页面摘要] 面板可返回一组丰富的量度数据和可视化图表，以帮助您更好地了解有关特定页面的统计信息。

| 量度/可视化图表 | 描述 |
| --- | --- |
| [!UICONTROL 页面查看次数]  — 当前月份，到目前为止 | 当月此页面的页面查看次数。 |
| [!UICONTROL 页面查看次数] - 4周前 | 上个月此页面的页面查看次数。 |
| [!UICONTROL 页面查看次数] - 52周前 | 去年此页面的页面查看次数。 |
| [!UICONTROL 趋势] | 本月、4周前和52周前的趋势页面查看图表。 |
| [!UICONTROL 占所有页面查看次数的百分比] | 浏览到此页面的所有页面查看次数的百分比概要数字。 |
| [!UICONTROL 页面逗留时间] | 列出此页面逗留时间的水平条形图。 |
| [!UICONTROL 单页面访问量] | 列出这是唯一访问的页面的页面查看次数的概要数字。 |
| [!UICONTROL 重新载入] | 此 [!UICONTROL 重新载入] 量度显示重新加载期间维度项目存在的次数。 访客刷新其浏览器是触发重新载入的最常见方式。 |
| [!UICONTROL 登录] | 此 [!UICONTROL 条目] 量度显示给定维度项目被捕获为访问中第一个值的次数。 |
| [!UICONTROL 退出] | 此 [!UICONTROL 退出点] 量度显示给定维度项目被捕获为访问中的最后一个值的次数。 |
| [!UICONTROL 流] | 以选定页面为焦点的流程图。 您可以像在任意 [流程图](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

![页面摘要](assets/page-sum1.png)面板

![量度和流量](assets/page-sum2.png)
