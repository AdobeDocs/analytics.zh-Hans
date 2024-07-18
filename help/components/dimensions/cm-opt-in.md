---
title: 同意管理选择加入
description: 查看访客选择加入的隐私设置。
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 91%

---

# 同意管理选择加入

“同意管理选择加入”维度[维度](overview.md)显示访客已选择加入哪些隐私设置。 您可以使用此维度根据隐私设置过滤数据，或查看最常见的隐私选择加入原因。

## 使用数据填充此维度

此维度从以下[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)收集数据：

* `contextData.['opt.dmp']`（当设置为 `Y`）。如果 `opt.dmp` 等于 `N`，则改为填充[同意管理选择退出](cm-opt-out.md)维度。
* `contextData.['opt.sell']`（当设置为 `Y`）。如果 `opt.sell` 等于 `N`，则改为填充[同意管理选择退出](cm-opt-out.md)维度。

您的组织确定实现这些上下文数据变量的逻辑。它们在点击之后便不再存在，因此您必须在每个页面上设置每个上下文数据变量。

## 维度项

维度项包括以下两个值：

* **`DMP`**：访客选择分享到数据管理平台。此维度项在上下文数据变量 `opt.dmp` 等于 `Y` 时存在。
* **`SELL`**：访客选择向第三方共享或出售数据。此维度在上下文数据变量 `opt.sell` 等于 `Y` 时存在。
