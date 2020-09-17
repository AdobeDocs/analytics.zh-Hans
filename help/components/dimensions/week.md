---
title: 周
description: 量度出现的周。
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 42%

---


# 周

“周”维度会报告给定量度出现的周。第一个维度项目是日期范围内的第一周，最后一个维度项目是日期范围内的最后一周。 此维度对趋势报表而言非常重要，因为它允许您查看一段时间内的量度变化情况。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## Dimension项

在Analysis Workspace，维度项目包括一周中第一天的日期（月、日和年）。

在Data warehouse中，维度项目包含基于请求日期范围的编号周。 例如，第一个整周是 `"Week 1"`。 如果请求包含部分周，则数据将分组到维项目中 `"Week 0"`。
