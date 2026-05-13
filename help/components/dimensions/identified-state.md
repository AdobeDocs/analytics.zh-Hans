---
title: 识别的状态
description: 确定拼接识别的标志。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 111
ht-degree: 82%

---

# 识别的状态

“识别的状态”[维度](overview.md)特定于[跨设备分析](../cda/overview.md)虚拟报表包。 它报告在运行报表时系统是否识别（拼接）了点击。 此维度有助于了解 CDA 拼合或“压缩”数据的效果。

## 使用数据填充此维度

只要您为虚拟报表包配置了[跨设备分析](../cda/overview.md)，就可以随时使用此维度。

## 维度项目

维度项目包括 `"Identified"` 和 `"Unidentified"`。

* **`"Identified"`**：点击映射到人员。
* **`"Unidentified"`**：点击未映射到人员，也无法被任何归因方法所映射。
