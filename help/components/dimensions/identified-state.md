---
title: 已识别状态
description: 由设备图确定识别的标志。
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 9%

---


# 已识别状态

“已识别状态”维特定于[跨设备分析](../cda/overview.md)虚拟报告套件。 它报告在运行报告时，设备图表是否识别Experience CloudID。 此维度有助于了解CDA拼接或“压缩”数据的效果。

## 使用数据填充此维度

只要您为虚拟报告套件配置了[跨设备分析](../cda/overview.md)，此维度就会开箱即用。

## 维度项目

维度项目包括 `"Identified"` 和 `"Unidentified"`。

* **`"Identified"`**:设备图识别与点击关联的Experience CloudID。
* **`"Unidentified"`**:设备图表无法识别Experience CloudID，或点击没有Experience CloudID。
