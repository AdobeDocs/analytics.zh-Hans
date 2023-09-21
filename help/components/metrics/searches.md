---
title: 搜索
description: 点击与外部搜索条件匹配的次数。
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 88%

---

# 搜索

“搜索” [量度](overview.md) 显示与Adobe的外部搜索检测匹配的点击数。 当您想要查看非搜索维度项目，并了解它们对搜索引擎流量的贡献时，此量度非常有用。

## 如何计算此量度

此量度计算与 Adobe 的外部搜索检测匹配的点击数。它必须与以下两项相匹配：

* 点击的反向链接值是 Adobe 识别的搜索域
* 点击的反向链接 URL 包含关键词查询字符串参数。由于现代隐私惯例，此查询字符串值通常为空。Adobe 将空白关键词查询字符串识别为搜索检测的一部分。
