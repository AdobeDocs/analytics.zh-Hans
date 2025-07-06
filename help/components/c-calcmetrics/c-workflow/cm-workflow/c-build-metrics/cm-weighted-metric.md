---
description: 了解过滤和加权量度的示例。
title: 过滤和加权量度
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 63%

---

# 过滤和加权指标

本文显示了过滤和加权量度的示例。

## 过滤的跳出率

这个简单的过滤量度仅显示访问次数超过 100 的页面的跳出率：

![已过滤的跳出率](assets/filtered-bounce-rate.png){zoomable="yes"}

请记住，此公式依赖于一致的时间范围。如果您运行报表的时间范围为一天，则任何访问次数超过 20 的页面都值得查看。如果您运行报表的时间范围为一个月，则可能希望过滤器包含更多的访问次数。

## 带百分位数的过滤跳出率

此过滤器在按访问量排序时，显示排名前30%页面的跳出率。

![已筛选的跳出率（百分点为](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}）

## 加权跳出率

假定您希望大致按跳出率排序，但具有更多访问次数的页面应当在列表中的排位更高。您可以创建与如下所示类似的加权跳出率：

![](assets/weighted-bounce-rate.png)
