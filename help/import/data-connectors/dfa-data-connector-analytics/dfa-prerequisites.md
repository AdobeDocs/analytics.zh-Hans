---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: 先决条件
solution: Analytics
title: 先决条件
topic: Data connectors
uuid: b5f5e30c-e269-41a4-923-6ddc404 bfd94
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 先决条件{#prerequisites}

在开始 DFA 的 Adobe Data connectors 集成之前，请执行以下操作：

* 决定集成是针对版本 1.5 的集成，还是等待版本 2.0。此决定取决于您的 DFA 帐户中所应用的具体功能，以及您希望进行集成的时间范围。请参阅[关于版本 2.0](../dfa-data-connector-analytics/dfa-version-differences.md#concept-2c7d6a6ab8524dccad96ea0c17228664)，以获取更多信息。
* 决定 DFA 广告商将如何映射到 Adobe Analytics 报表包。例如，如果您具有多个 DFA 广告商和多个报表包，您将需要决定哪些广告商与哪些报表包配对。
* 使用版本 H.22 或更高版本的数据收集代码，在希望跟踪的所有页面上实施 Adobe 数据收集代码。
* 知晓要集成的 Floodlight 配置的 DFA 帐户的广告商 ID。集成可自动导入 Floodlight 配置范围内的所有广告商。
* 知晓 DFA 帐户的用户名和密码。
* 将每个 DFA 广告商只关联到一个 Adobe Analytics 报表包。对多个报表包进行标记不受 DFA 的默认 Genesis 集成支持。
* 针对将成为集成一部分的每个 DFA 版面，将一个点进查询字符串参数添加到其登陆页面。此查询字符串参数是正确统计点进次数所必需的。
* 配置您的 DFA 版面，这样它们就不会将访客重定向到多个域。例如，版面不应将响应者定向到 www.xyz.com 下托管的微型网站（如果该微型网站随后会将他们重定向到另一网站 www.fgh.com 的话）。如果促销活动响应跨越多个域，则点进和显示到达数据可能被夸大并具有误导性。
* 在报告与分析中标识一个自定义变量，以保留您的促销活动信息。
* 标识报告与分析 eVar 以存储 DFA 显示到达信息。将此 eVar 仅用于该 DFA 集成。
* 标识要在其中存储展示和点击数据的报告与分析事件。您可能要适当地重命名这些事件。
* （可选）标识将存储 DFA 成本数据的报告与分析事件。您可能要适当地重命名这些事件。
* （可选）标识将存储 DFA 错误和超时的报告与分析自定义变量和成功事件。这些变量有助于诊断集成可能出现的问题。
* （可选）创建一个特殊的电子邮件帐户，用于接收与 DFA 的 Data connectors 集成相关的信息和通知。

