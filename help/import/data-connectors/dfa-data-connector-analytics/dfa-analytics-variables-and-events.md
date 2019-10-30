---
description: DFA 的 Data connectors 集成使用 Analytics 变量来跟踪 DFA 促销活动结果。
keywords: DFA
seo-description: DFA 的 Data connectors 集成使用 Analytics 变量来跟踪 DFA 促销活动结果。
seo-title: Analytics 变量和事件
solution: Analytics
title: Analytics 变量和事件
topic: Data connectors
uuid: 8996cb58-c793-4600-99ef-af3064642b29
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Analytics 变量和事件{#analytics-variables-and-events}

DFA 的 Data connectors 集成使用 Analytics 变量来跟踪 DFA 促销活动结果。

除了促销活动变量，您还可以根据需要使用 Analytics 事件和 eVar。在标识了此 DFA 集成要使用的事件和 eVar 之后，请使用 Analytics 管理控制台启用它们。集成变量必须在激活 DFA 集成之前启用。下表描述了 DFA 集成所需要的 Analytics 变量。

| 变量 | 友好名称 | 填充方法 | 描述 |
|---|---|---|---|
| s.campaign 或 eVar | 广告跟踪代码 | 由 DFA 促销活动的 Data Connectors 自动填充。 | 跟踪所有促销活动的点进转化。 |
| eVar* | 显示到达 | 由 DFA 促销活动的 VISTA 和 DFA 自动填充。 | 跟踪 DFA ID 的显示到达数据。此 eVar 应当具有与 *`s.campaign`* 变量捕获。必须是变量提供者ID中标识的相同转换变量。 确保 eVar 启用了完全子关系。启用此功能的成本属于 Data connectors 集成费用的一部分 |
| eVar* | DFA 查询错误 | （可选）已通过 JavaScript 收集代码填充。 | 包含从DFA返回的多个错误代码之一。 |
| 事件* | 显示到达计数 | 由 DFA 促销活动的 Data Connectors 自动填充。 | 捕获用户查看某广告后没有点进但访问了您的网站的次数。 |
| 事件* | 展示次数 | 通过来自 DFA 的数据馈送自动填充。 | 跟踪特定 DFA 广告服务的提供次数。 |
| 事件* | 点击量 | 通过来自 DFA 的数据馈送自动填充。 | 跟踪用户点击特定 DFA 横幅广告的次数。此量度可能出于某些原因之一产生不同于本地 Analytics 点进量度的数字。请参阅[协调量度差异](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md)，以获取更多信息。 |
| 事件* | DFA 超时 | （可选）已通过 JavaScript 收集代码填充。 | 统计 DFA 在&#x200B;*`s.maxDelay`*&#x200B;超时之前响应失败的次数。这有助于您确定是否存在 DFA 实施问题。 |
| 事件* | DFA 媒体成本 | 通过来自 DFA 的数据馈送自动填充。 | 包含已在 DFA 界面中输入的媒体成本量度。此功能必须在 DFA 端启用，以便使这些量度显示。 |

*选择未使用的 eVar 或自定义事件。
