---
title: 小时
description: 量度出现的小时。
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
TQID: https://experienceleague.adobe.com/Gkigdxnrted-gkPoGCQMx229EvCmVvSt9Rr5QP-IfGU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 94%

---

# 小时

“小时”[维度](overview.md)报告给定量度出现的小时（向下舍入）。 第一个维度项目是日期范围内的第一个小时，最后一个维度项目是日期范围内的最后一个小时。 此维度对趋势报表而言非常重要，因为它允许您查看一段时间内的量度变化情况。

## 使用数据填充此维度

此维度可开箱即用于所有实施。 如果报表包包含数据，则此维度有效。

## 维度项目

维度项目包括报表日期范围内的给定小时及其日期。 其格式为 `HH:HH YYYY-MM-DD`。

## 夏令时

夏令时是一种在春季将时钟拨快一个小时，在秋季将时钟拨回一个小时的做法。 如果报表包的时区使用夏令时，则 Adobe 将相应地调整该小时的数据。

* **夏令时开始时**：在 3 月份，报表通常会在夏令时开始时在数据中显示一小时的空档。 这个小时并不存在，因此它不是数据收集的一部分。 请注意，少量数据仍然可以归入到这一小时中。 Adobe 数据收集服务器需要花费几秒钟（最多一分钟）时间来将夏令时调整考虑在内。
* **夏令时结束时**：在 11 月份，报表通常会在夏令时结束时显示两个堆叠的小时。 这个小时出现了两次，因此这两个小时都会在报表中汇总。
