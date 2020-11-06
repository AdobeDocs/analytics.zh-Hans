---
title: 每次访问的平均页面查看次数
description: 给定维度项目在一次访问中出现的平均次数。
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 93%

---


# 每次访问的平均页面查看次数

“每次访问的平均页面查看次数”维度显示针对所需维度平均查看页面的次数。对于基于时间的维度，您可以查看访问中一段时间内平均页面查看次数的趋势。当您想要了解维度项目在访问中出现的频率时，此量度非常有用。

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. 如果您单独使用此量度，则会获得包含每次访问异常页面查看次数的维度项目，该维度项目通常没有什么价值。

## 如何计算此量度

使用公式 [`Page views`](page-views.md)` divided by `[`Visits`](visits.md) 计算此量度。

## 百分比高于 100%

此量度通常包含高于 100% 的百分比。分母是整个维度的每次访问平均页面查看次数，分子是维度项目的每次访问平均页面查看次数。如果整个维度的每次访问平均页面查看次数少于给定维度项目的每次访问平均页面查看次数，您将看到高于 100% 的百分比。按此量度对排名报表进行排序，会显示每次访问平均页面查看次数的异常值，该值通常没什么价值。Adobe 建议在排名报表中按其他量度（例如[访问次数](visits.md)）来排序。