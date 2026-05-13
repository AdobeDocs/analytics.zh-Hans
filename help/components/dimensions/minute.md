---
title: 分钟
description: 量度出现的分钟。
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
TQID: https://experienceleague.adobe.com/GRivRprXBteGxRZieSI3uyjHALDJ-0hHbZx3S9ldJW0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 76%

---

# 分钟

“分钟”[维度](overview.md)报告给定量度出现的分钟（向下舍入）。 第一个维度项目是日期范围内的第一分钟，最后一个维度项目是日期范围内的最后一分钟。 此维度对趋势报表而言非常重要，因为它允许您查看一段时间内的量度变化情况。 考虑到此维度的精细程度，Adobe 建议将报表日期范围限制为一天或两天。

## 使用数据填充此维度

此维度可开箱即用于所有实施。 如果报表包包含数据，则此维度有效。

## 维度项目

维度项目包括报表日期范围内的给定分钟及其日期。 其格式为 `HH:MM YYYY-MM-DD`。 以`00:00`开头的Dimension项目等于当天的午夜，而以`23:59`开头的值等于当天的晚上11:59。
