---
description: DFA 的 Data connectors 集成使用 Analytics 变量来跟踪 DFA 促销活动结果。
keywords: DFA
seo-description: DFA 的 Data connectors 集成使用 Analytics 变量来跟踪 DFA 促销活动结果。
seo-title: Analytics 变量和事件
solution: Analytics
title: Analytics 变量和事件
topic: Data connectors
uuid: 8996cb58-c793-4600-99ef-af3064642 b29
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics 变量和事件{#analytics-variables-and-events}

DFA 的 Data connectors 集成使用 Analytics 变量来跟踪 DFA 促销活动结果。

除了促销活动变量，您还可以根据需要使用 Analytics 事件和 eVar。在标识了此 DFA 集成要使用的事件和 eVar 之后，请使用 Analytics 管理控制台启用它们。集成变量必须在激活 DFA 集成之前启用。下表描述了 DFA 集成所需要的 Analytics 变量。

| 变量 | 友好名称 | 填充方法 | 描述 |
|---|---|---|---|
| s.campaign 或 eVar | 广告跟踪代码 | 由 DFA 促销活动的 Data Connectors 自动填充。 | 跟踪所有促销活动的点进转化。 |
| eVar* | 显示到达 | 由 DFA 促销活动的 VISTA 和 DFA 自动填充。 | 跟踪 DFA ID 的显示到达数据。此 eVar 应当具有与&#x200B;*`s.campaign`* 变量。Must be the same conversion variable as identified in the Variable Provider ID (See [Update Your Website’s Data Collection Code](../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)). 确保 eVar 启用了完全子关系。启用此功能的成本属于 Data connectors 集成费用的一部分 |
| eVar* | DFA 查询错误 | （可选）已通过 JavaScript 收集代码填充。 | 包含从 DFA 返回的几个错误代码之一（请参阅[配置集成](../dfa-data-connector-analytics/dfa-integration/dfa-integration.md#concept-cf33e1051c73452cbd26e950d0293858)中列有这些错误代码的表格） |
| 事件* | 显示到达计数 | 由 DFA 促销活动的 Data Connectors 自动填充。 | 捕获用户查看某广告后没有点进但访问了您的网站的次数。 |
| 事件* | 展示次数 | 通过来自 DFA 的数据馈送自动填充。 | 跟踪特定 DFA 广告服务的提供次数。 |
| 事件* | 点击量 | 通过来自 DFA 的数据馈送自动填充。 | 跟踪用户点击特定 DFA 横幅广告的次数。此量度可能出于某些原因之一产生不同于本地 Analytics 点进量度的数字。请参阅[协调量度差异](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f)，以获取更多信息。 |
| 事件* | DFA 超时 | （可选）已通过 JavaScript 收集代码填充。 | 统计 DFA 在&#x200B;*`s.maxDelay`*&#x200B;超时之前响应失败的次数。这有助于您确定是否存在 DFA 实施问题。 |
| 事件* | DFA 媒体成本 | 通过来自 DFA 的数据馈送自动填充。 | 包含已在 DFA 界面中输入的媒体成本量度。此功能必须在 DFA 端启用，以便使这些量度显示。 |

*选择未使用的 eVar 或自定义事件。
