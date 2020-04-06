---
description: 'null'
keywords: DFA
title: 常见问题解答
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 常见问题解答{#frequently-asked-questions}

## Data Connectors 向导为何不接受我的登录凭据？{#section-f019b3de18774df3954af7881aa564fa}

如果您已验证登录凭据是有效的，则下一步验证为集成提供的用户名是否已启用API访问。 数据连接器向导使用DFA API验证登录凭据，以及在DFA API中关闭和打开特定于Adobe的设置。 API访问是管理员必须从DFA界面中打开的设置。 接下来，确保您拥有访问向导中选择的广告商ID或Floodlight配置ID的权限。

## 为什么我看不到任何来自晚间上传指标的数据（DFA印象、DFA点击等）? {#section-465fd22ae6b447ffb6baf20b57daa433}

如果您使用的是版本1.5的集成，这可能是因为您的集成尚未分配客户端站点ID。 要进行夜间交换，并从DFA广告服务器请求数据，需要客户端站点ID(CSID)。 CSID在集成日期起最多可用3天与Google交换。 在从 Google 收到 CSID 后，系统将通过集成中新 CSID 的电子邮件地址向您发送通知，以及最新的 JavaScript 代码。

如果已超过3天，但您尚未收到设置电子邮件，且量度不会流动，则最可能的问题是CSID已分配给其他集成。 Google维护CSID和报表包之间的1到1映射，这意味着如果一个报表包中的集成使用与另一个报表包中的另一个集成相同的广告商ID，则只会为第一个集成分配CS ID。 要更改CSID映射到的报表包或广告商ID，必须在Google支持部门中打开票证。

例如，假设报表包A中集成了广告商ID Z，该集成会被分配一个CSID。 如果稍后在包含广告商Z的报表包B中设置了另一个集成，则不会为此较新的集成重新分配CSID。 这需要谷歌的票。 另一方面，以报表包A中与广告商ID Z的集成为例，随后将设置报表包A中与广告商Z的其他集成。 只有第一个集成会收到集成的数据；但是，在这种情况下，可以取消激活第一集成，并且数据将流向第二集成。

>[!NOTE] CSID 未在版本 2.0 的集成中使用，因此 CSID 协商过程不适用。

## 我使用的是版本2.0的集成，且DFA广告中不显示成本指标。 为什么会这样？ {#section-805748111bbe4bbf918d6dbbb2641fff}

必须从Google DFA端打开成本指标，并在DFA界面中提供，以及在数据连接器向导中打开成本指标。 首先需要验证的是，您已经为DFA媒体成本映射了分析事件，并提供了货币代码。 如果您已映射“媒体成本事件”，并完成并保存向导，则DFA API中将打开DFA omnitureCostData标志。 这将向谷歌发出信号，指标应在晚间文件中发送。 您可以通过DFA界面多次检查通过查看集成Floodlight上的属性来启用omnitureCostData。 最后，在检查这两个位置后，确保作为集成Floodlight的一部分的广告指定成本数据和成本结构。 如果成本数据未在DFA界面中提供，则它不会显示在Analytics中。

## 为什么某些广告不显示任何DFA展示或视图次数，但却显示点击和点进次数？ {#section-39b2eeeefd7f43d1a373df0b987bacef}

有些广告只记录点击数据，称为点击跟踪器。 这些类型的广告不会从查询Floodlight服务器时返回最后印象数据。 要验证某个广告是点击跟踪器还是仅点击广告，请与您的DFA代理或Google支持代表联系。

## 为何没有显示 DFA 点击量的任何广告点进次数？{#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

这个问题有很多答案。

首先，检查相关广告是否有登陆页URL，该URL是(a)用您查看的同一报表包的Adobe代码标记，并且(b)包含查询字符串参数。 *`clickThroughParam`*

然后，通过执行[确认 DFA 集成成功](../dfa-data-connector-analytics/dfa-integration.md)中的步骤，验证集成是否正常工作。如果您在登陆页面中看到包含 Adobe 点击的 DFA 跟踪代码，则应当在 DFA 促销活动报表中看到该点进。如果未看到该点进，请验证登陆页面的 *`s.account`* 变量与在 Reports &amp; Analytics 中查看的报表包是否匹配。如果这些匹配，请检查“通过eVar视图”报表中的跟踪代码，这些代码看起来像DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX。

这表示DFA VISTA规则无法从DFA中摘要原始数据。 通过您的Adobe帐户代表打开支持票证可以解决此问题。

如果上述解决方案都未解释问题，请参阅协调 [度量差异](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) ，以探索其他可能性。
