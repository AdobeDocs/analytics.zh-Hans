---
title: 周
description: 量度出现的周。
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 92%

---

# 周

“周”[维度](overview.md)报告给定量度出现的周。 第一个维度项目是日期范围内的第一周，最后一个维度项目是日期范围内的最后一周。此维度对趋势报表而言非常重要，因为它允许您查看一段时间内的量度变化情况。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## 维度项目

在 Analysis Workspace 中，维度项包括该周第一天的日期（月、日和年）。

在 Data Warehouse 中，维度项包括基于请求日期范围的编号周。例如，第一个完整的一周为 `"Week 1"`。如果请求包括一周的一部分，则数据会分组到维度项 `"Week 0"`。
