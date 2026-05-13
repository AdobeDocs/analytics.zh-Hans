---
title: 同意管理选择加入
description: 查看访客选择加入的隐私设置。
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
TQID: https://experienceleague.adobe.com/hvtKcglMPFz4FbInpuSs9haS5SwGNQpVWXn12M1x658
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 90%

---

# 同意管理选择加入

“同意管理选择加入”维度[维度](overview.md)显示访客已选择加入哪些隐私设置。 您可以使用此维度根据隐私设置过滤数据，或查看最常见的隐私选择加入原因。

## 使用数据填充此维度

此维度从以下[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)收集数据：

* `contextData.['opt.dmp']`（当设置为 `Y`）。 如果 `opt.dmp` 等于 `N`，则改为填充[同意管理选择退出](cm-opt-out.md)维度。
* `contextData.['opt.sell']`（当设置为 `Y`）。 如果 `opt.sell` 等于 `N`，则改为填充[同意管理选择退出](cm-opt-out.md)维度。

您的组织确定实现这些上下文数据变量的逻辑。 它们在点击之后便不再存在，因此您必须在每个页面上设置每个上下文数据变量。

## 维度项目

维度项包括以下两个值：

* **`DMP`**：访客选择分享到数据管理平台。 此维度项在上下文数据变量 `opt.dmp` 等于 `Y` 时存在。
* **`SELL`**：访客选择向第三方共享或出售数据。 此维度在上下文数据变量 `opt.sell` 等于 `Y` 时存在。
