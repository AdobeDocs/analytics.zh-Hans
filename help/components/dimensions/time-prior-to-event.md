---
title: 发生事件之前逗留的时间
description: 量度与访问的首次点击之间的间隔时间。
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 84%

---

# 发生事件之前逗留的时间

“发生事件之前逗留的时间”维度[维度](overview.md)报告访问的首次点击与所需量度之间经过的时间量。 确定达到成功事件（例如，提交表单或购买）所花费的时间时，此维度非常有用。

## 使用数据填充此维度

虽然从技术上讲，此维度可开箱即用于所有实施，但它最适合于自定义事件和购买事件。 Adobe 建议您在自己的网站上实施自定义事件。 如果您实施自定义事件，则此维度无需任何其他实施。

## 维度项目

维度项目包括基于时间的时段，介于 `"Less than 1 minute"` 到 `"More than 15 hours"` 之间。 例如，如果访客从第一次点击到购买用了 23 分钟，则它属于 `"10 to 30 minutes"` 维度项目下。 无法为此量度自定义存储桶。
