---
title: 算法归因
description: 有关算法归因模型的详细信息。
feature: 归因
role: Business Practitioner, Administrator
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '258'
ht-degree: 100%

---

# 算法归因

Analysis Workspace 中的算法[归因模型](models.md)与其他模型有所不同，因为该模型会使用统计技术为报表或自由格式表中的各维度项目分配点数。与 Analysis Workspace 中的所有其他归因模型一样，该模型也可以用于任何维度或量度，支持无限分段和划分，并为表中的维度分配 100% 的转化率（因而也称为“分数”归因）。

归因算法基于合作博弈理论中的 Harsanyi Dividend 算法。Harsanyi Dividend 算法是对“沙普利值”解决方案（以诺贝尔经济学奖获得者罗伊德·沙普利 (Lloyd Shapley) 命名）的推广形式，用于为对结果具有不同贡献的各参与者分配功能值（点数）。

概言之，在对每个接触点的转化点数进行归因计算时，会将回顾时间范围内的每个营销接触点视为由各参与者组成的联盟，其中必须在每位参与者之间平均分配剩余价值。按照递归方式，每个联盟的剩余价值分配取决于由先前的每个子联盟（即先前参与的维度项目）产生的剩余价值。有关更多详细信息，请参阅约翰·海萨尼 (John Harsanyi) 和罗伊德·沙普利的原文：

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>仅当指定的回顾时间范围内存在多个接触点时，算法归因的结果才会与其他模型不同。无论使用何种归因模型，具有单个接触点的转化均可获得 100% 的点数。
