---
description: 'null'
title: 算法属性
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
translation-type: tm+mt
source-git-commit: b5418e6321b09ddbab36e0052f75f36067086e3e

---


# 算法属性

![算法](assets/algorithmic.png)

Analysis Workspace中 [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html#attribution-models) 的算法归因模型与Attribution IQ中的其他模型不同，它使用统计技术在报表或自由表格的维值中分配信用。 与Analysis Workspace中的所有其他归因模型一样，该模型可用于任何维度或度量，并支持无限细分和细分，并将100%的转化率分布到表中的维（也称为“分数”归因）。

基于合作博弈论的Harsanyi Danyis算法用于归因。 哈萨尼派息是沙普利价值解决方案（以诺贝尔经济学奖得主劳埃德·沙普利命名）的泛泛化，旨在在一场对结果贡献不均的游戏中为玩家分配信用。

在高层面，每个接触点的转化信用的归因计算将回顾窗口内的每个营销接触点视为必须公平分配盈余的玩家联盟。 每个联盟的剩余分配根据每个子联盟先前创建的剩余（或先前参与的维值）递归确定。 有关更多详细信息，请参阅John Harsanyi和Lloyd Shapley的原始文章：

* 沙普利，劳埃德·S。“N人游戏的价值。” 对博弈论的贡献2.28(1953):307-317。

* Harsanyi, John C.“n人合作博弈的简化谈判模式。” 《国际经济评论》第4.2（1963年）:194-220年。

*注意：当给定回顾窗口中存在多个接触点时，算法归因的结果仅与其他模型不同。 例如，只有一个接触点，无论选择的归因模型如何，100%的信用将分配给该值。*