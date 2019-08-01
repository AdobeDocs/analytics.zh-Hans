---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: 常见问题解答
solution: Analytics
title: 常见问题解答
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981 f87 c9372
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 常见问题解答{#frequently-asked-questions}

## Why won’t the Data Connectors wizard accept my login credentials? {#section-f019b3de18774df3954af7881aa564fa}

如果您已验证登录凭据确实有效，下一步请验证为集成提供的用户名是否已针对 API 访问启用。Data connectors 向导使用 DFA API 验证登录凭据，并且在 DFA API 中打开和关闭特定 Adobe 设置。API 访问这项设置必须由管理员从 DFA 界面内打开。接下来，确保您有权访问在向导中选择的广告商 ID 或 Floodlight 配置 ID。

## 我为何没有看到任何来自夜间上载量度的数据（DFA 展示次数、DFA 点击量等）？ {#section-465fd22ae6b447ffb6baf20b57daa433}

如果您使用的是 1.5 版本的集成，则可能是因为您的集成尚未分配到任何客户端站点 ID。要进行夜间数据交换和请求来自 DFA 广告服务器的数据，都需要客户端站点 ID (CSID)。自集成日起，需要最多 3 天时间与 Google 交换 CSID。在从 Google 收到 CSID 后，系统将通过集成中新 CSID 的电子邮件地址向您发送通知，以及最新的 JavaScript 代码。

如果超过三天以后您还未收到设置电子邮件且量度没有流通，则最有可能的问题是 CSID 已被分配给其他集成。Google 会保持 CSID 和报表包之间一对一的映射，这意味着如果某个报表包中的集成使用与其他报表包中其他集成相同的广告商 ID，则只有第一个集成将分配到 CS ID。要更改 CSID 所映射到的报表包或广告商 ID，必须通过 Google 支持打开一个票证。

例如，假设具有广告商 ID Z 的报表包 A 中有一个分配有 CSID 的集成。如果后来在具有广告商 Z 的报表包 B 中设置另一个集成，将不会为这个较新的集成重新分配 CSID。这将需要 Google 票证。另一方面，如果具有广告商 ID Z 的报表包 A 中有一个集成，后来在具有广告商 Z 的报表包 A 中设置另一个集成。则只有第一个集成将收到集成的数据；但是在这种情况下，第一个集成可以被停用，而数据将流向第二个集成。

>[!NOTE]
>
>CSID未在集成的版本2.0中使用，因此CSID协商过程不适用。

## 我使用的是 2.0 版本的集成，但是未对我的 DFA 广告显示成本量度。为什么会这样？ {#section-805748111bbe4bbf918d6dbbb2641fff}

成本量度必须在 Google DFA 端打开并且在 DFA 界面中提供，同时在 Data connectors 向导中打开。首先要验证您已经为 DFA 媒体成本映射了一个 Analytics 事件，并提供了货币代码。如果您已映射媒体成本事件，并完成和保存向导，将在 DFA API 中打开 DFA omnitureCostData 标记。这将向 Google 发出信号，指示量度应在夜间文件中发送。您可以通过 DFA 界面查看集成 Floodlight 中的属性，以再次确认 omnitureCostData 是否已启用。最终，在检查了这两个位置之后，请确保属于集成 Floodlight 一部分的广告指定了成本数据和成本结构。如果成本数据未在 DFA 界面中提供，它将不会在 Analytics 中显示。

## 为何某些广告不显示任何 DFA 展示次数或显示到达次数，但它们却会显示点击量和点进次数？ {#section-39b2eeeefd7f43d1a373df0b987bacef}

有一些广告只记录点击数据，因此被称为点击跟踪器。这种类型的广告不返回自上次查询 Floodlight 服务器以来的最新展示数据。要验证某个广告是点击跟踪器还是纯点击广告，请联系您的 DFA 代理或 Google 支持代表。

## 为何没有显示 DFA 点击量的任何广告点进次数？ {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

此问题可能存在多个答案。

首先，请检查所涉及的广告的登陆页面 URL 是 (a) 通过您查看差异时所在的相同报表包的 Adobe 代码进行标记，并且 (b) 包含&#x200B;*`clickThroughParam`*&#x200B;查询字符串参数。

Second, verify that you have a working integration by following through the steps in [Confirming a Successful DFA Integration](../dfa-data-connector-analytics/dfa-integration/dfa-confirm-integration.md#concept-c1c869d2a6fa46b09fe41fc286e407c6). 如果您在登陆页面中看到包含 Adobe 点击的 DFA 跟踪代码，则应当在 DFA 促销活动报表中看到该点进。如果没有看到，请验证报表包匹配登陆页面的&#x200B;*`s.account`*&#x200B;变量，并且可以在报告与分析中查看该报表包。如果它们匹配，请在显示到达 eVar 报表中检查跟踪代码，类似于 DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX。

它们指示 DFA VISTA 规则未能分类来自 DFA 的原始数据。通过您的 Adobe 帐户代表打开一个支持票证，可修复此问题。If none of the solutions above explain the problem, see [Reconciling Metric Discrepancies](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f) to explore other possibilities