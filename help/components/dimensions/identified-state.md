---
title: 识别的状态
description: 确定拼接识别的标志。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: f75a1f6d9f08f422595c24760796abf0f8332ddb
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 83%

---

# 识别的状态

“识别的状态”[维度](overview.md)特定于[跨设备分析](../cda/overview.md)虚拟报表包。 它报告在运行报表时系统是否识别（拼接）了点击。此维度有助于了解 CDA 拼合或“压缩”数据的效果。

## 使用数据填充此维度

只要您为虚拟报表包配置了[跨设备分析](../cda/overview.md)，就可以随时使用此维度。

## 维度项目

维度项目包括 `"Identified"` 和 `"Unidentified"`。

* **`"Identified"`**：点击映射到人员。
* **`"Unidentified"`**：点击未映射到人员，也无法被任何归因方法所映射。
