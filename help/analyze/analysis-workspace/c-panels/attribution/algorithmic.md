---
title: 算法归因
description: 有关Adobe Analytics中算法归因模型的详细信息。
translation-type: tm+mt
source-git-commit: 59ca7a8b6f067d62c4abea572c199fb95897d854

---


# 算法归因

> [!NOTE] 算法归因目前仅通过 [Adobe Analytics实验室提供](https://docs.adobe.com/content/help/en/analytics/analyze/tech-previews/overview.html)。 该功能最终将成为一般版本的一部分。

Analysis Workspace中 [的Algorithmic attribution模型与其他模型不同之处在于](attribution.md) ，它使用统计技术在报表或自由格式表中的维值之间分配信用。 与Analysis Workspace中的所有其他归因模型一样，该模型可用于任何维度或度量，并支持无限细分和细分，并将100%的转化率分布到表中的维（也称为“分数”归因）。

基于合作博弈论的Harsanyi Danyis算法用于归因。 哈萨尼派息是沙普利价值解决方案（以诺贝尔经济学奖得主劳埃德·沙普利命名）的泛泛化，旨在在一场对结果贡献不均的游戏中为玩家分配信用。

在高层面，每个接触点的转化信用的归因计算将回顾窗口内的每个营销接触点视为必须公平分配盈余的玩家联盟。 每个联盟的剩余分配根据每个子联盟先前创建的剩余（或先前参与的维值）递归确定。 有关详细信息，请参阅John Harsanyi和Lloyd Shapley的原始文章：

* 沙普利，劳埃德·S。(1953)。 n人游戏的价值。 *对游戏理论的贡献，2(28)*,307-317。
* Harsanyi, John C.(1963)。 n人合作博弈的简化讨价还价模型。 *《国际经济评论》第4(2)*,194-220年。

> [!NOTE] 当给定回顾窗口中存在多个接触点时，算法归因的结果仅与其他模型不同。 无论归因模型如何，单个接触点的转化率都可获得100%的信用。
