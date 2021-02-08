---
title: 识别的状态
description: 一种用来确定是否被设备图识别的标志。
translation-type: ht
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: ht
source-wordcount: '120'
ht-degree: 100%

---


# 识别的状态

“识别的状态”维度是[跨设备分析](../cda/overview.md)虚拟报表包特有的维度。它可以报告在运行报表时，Experience Cloud ID 是否被设备图所识别。此维度有助于了解 CDA 拼合或“压缩”数据的效果。

## 使用数据填充此维度

只要您为虚拟报表包配置了[跨设备分析](../cda/overview.md)，就可以随时使用此维度。

## 维度项目

维度项目包括 `"Identified"` 和 `"Unidentified"`。

* **`"Identified"`**：设备图识别了与该点击关联的 Experience Cloud ID。
* **`"Unidentified"`**：设备图未识别 Experience Cloud ID，或者，该点击不包含 Experience Cloud ID。
