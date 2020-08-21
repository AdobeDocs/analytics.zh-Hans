---
title: 发生事件之前逗留的时间
description: 量度与访问的首次点击之间的间隔时间。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 78%

---


# 发生事件之前逗留的时间

“发生事件之前逗留的时间”维度报告访问的首次点击与所需量度之间经过的时长。确定达到成功事件（例如，提交表单或购买）所花费的时间时，此维度非常有用。

## 使用数据填充此维度

虽然从技术上讲，此维度可开箱即用于所有实施，但它最适合于自定义事件和购买事件。Adobe 建议您在自己的网站上实施自定义事件。如果您实施自定义事件，则此维度无需任何其他实施。

## Dimension项

Dimension items include time-based buckets ranging from `"Less than 1 minute"` to `"More than 15 hours"`. For example, if it took a visitor 23 minutes from their first hit to a purchase, it would belong under the `"10 to 30 minutes"` dimension item.
