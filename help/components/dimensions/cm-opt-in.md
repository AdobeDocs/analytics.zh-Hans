---
title: 同意管理选择加入
description: 查看访客选择加入的隐私设置。
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 7%

---

# 同意管理选择加入

“同意管理选择加入”维度显示访客已选择加入的隐私设置。 您可以使用此维度根据隐私设置过滤数据，或查看最常见的隐私选择加入原因。

## 使用数据填充此维度

此维度从以下内容收集数据 [上下文数据变量](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` 当设置为 `Y`. 如果 `opt.dmp` 等于 `N`, [同意管理选择退出](cm-opt-out.md) 维度将被填充。
* `contextData.['opt.sell']` 当设置为 `Y`. 如果 `opt.sell` 等于 `N`, [同意管理选择退出](cm-opt-out.md) 维度将被填充。

贵组织确定实施这些上下文数据变量的逻辑。 它们不会在设置的点击之后保留，因此您必须在每个页面上设置每个上下文数据变量。

## 维度项

Dimension项目包括以下两个值：

* **`DMP`**:访客选择共享到数据管理平台。 上下文数据变量时存在此维度项目 `opt.dmp` 等于 `Y`.
* **`SELL`**:访客选择将数据共享或出售给第三方。 上下文数据变量时存在此维度 `opt.sell` 等于 `Y`.
