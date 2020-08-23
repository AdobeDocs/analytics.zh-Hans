---
title: 每次访问的平均页面查看次数
description: 给定维度项目在访问中的平均显示次数。
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 46%

---


# 每次访问的平均页面查看次数

“每次访问的平均页面查看次数”维度显示针对所需维度平均查看页面的次数。对于基于时间的维度，您可以查看访问中一段时间内平均页面查看次数的趋势。当您想要了解访问中维度项目的显示频率时，此指标非常有用。

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. 如果您单独使用此度量，则您会获得包含每次访问异常页面视图的维度项目，这通常不有价值。

## 如何计算此量度

使用公式 [`Page views`](page-views.md)` divided by `[`Visits`](visits.md) 计算此量度。

## 百分比高于 100%

此量度通常包含高于 100% 的百分比。分母是整个维的每次访问的平均页面视图，分子是维项的每次访问的平均页面视图。 如果整个维度的每次访问平均页面视图数低于给定维度项目的每次访问平均页面视图数，您将看到100%以上的百分比。 按此量度对排名报表进行排序，会显示每次访问平均页面查看次数的异常值，该值通常没什么价值。Adobe 建议在排名报表中按其他量度（例如[访问次数](visits.md)）来排序。