---
title: 每天的某小时
description: 一天中的小时值，不考虑具体哪天。
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
TQID: https://experienceleague.adobe.com/cktusukSxy7fHIIUi-7MSmx8Gl9FlUObfmJGS3VC3Jw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 82%

---

# 每天的某小时

“小时”[维度](overview.md)将任何给定日期的小时数字报告为维度项目。 例如，如果某个报表的时间跨度为 1 月 1 日至 1 月 7 日，则每天的第一个小时会分组到同一个维度项目中。 当您希望报表按一天中的相对时间划分，但不希望静态小时作为维度项目时，此报表很有价值。 由于此维度会随着选定日期范围滚动，因此，将其作为计划报表中的维度特别有价值。

此维度基于报表包的时区，而不是访客的本地时区。 例如，如果您的报表包为山区时间，而加利福尼亚的访客在太平洋时间上午10:00访问您的网站，则点击将分组到`11:00 AM`维度项目下。 如果想要一个记录本地访客时间的维度，Adobe 建议使用 [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) 插件。

## 使用数据填充此维度

此维度可开箱即用于所有实施。 如果报表包包含数据，则此维度有效。

## 维度项目

维度项目包括 `12:00 AM` - `11:00 PM`，表示点击在一天中发生的小时（向下舍入）。 例如，如果点击是在下午3:58生成的，则它会分组到`3:00 PM`的维度项下。

## 夏令时

夏令时是一种在春季将时钟拨快一个小时，在秋季将时钟拨回一个小时的做法。 如果报表包的时区使用夏令时，则 Adobe 将相应地调整该小时的数据。

* **夏令时开始时**：在 3 月份，报表通常会在夏令时开始时在数据中显示一小时的空档。 这个小时并不存在，因此它不是数据收集的一部分。 请注意，少量数据仍然可以归入到这一小时中。 Adobe 数据收集服务器需要花费几秒钟（最多一分钟）时间来将夏令时调整考虑在内。
* **夏令时结束时**：在 11 月份，报表通常会在夏令时结束时显示两个堆叠的小时。 这个小时出现了两次，因此这两个小时都会在报表中汇总。
