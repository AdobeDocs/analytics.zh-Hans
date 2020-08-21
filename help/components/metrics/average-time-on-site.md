---
title: 网站平均逗留时间
description: 给定维度项目在点击之间存在的平均时间。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 63%

---


# 网站平均逗留时间

“站点平均时间”度量显示给定维度项目在点击之间传递的时间量。 当您要查看特定维度项目的平均花费时间时，此度量非常有用。 此外，您还可以跟踪此量度随时间的变化趋势，以了解总体逗留时间的变化情况。此量度以 `HH:MM:SS` 格式显示。

此量度与[每次访问逗留时间](../dimensions/time-spent-per-visit.md)维度相关。

## 如何计算此量度

对于给定的维项目，在该维项目存在的地方获取每次点击的时间戳。 对比访问中此次点击与下一次点击的时间戳。如果点击没有后续点击，请勿将该点击纳入此量度。在维项目所花费的所有时间中，将其全部除以该维项目的“序列”数。 “序列”是维项目对于一个或多个连续点击是相同的。 此结果数字是报表中显示的量度。

例如，请考虑以下访问：

| `Timestamp` | `Page` |
| --- | --- |
| `12:03:00` | `Home page` |
| `12:04:20` | `Product page A` |
| `12:05:30` | `Product page A` |
| `12:07:00` | `Product page B` |
| `12:07:40` | `Product page A` |
| `12:08:10` | `Checkout` |
| `12:10:00` | `Purchase` |
| `12:25:00` | `Home page` |
| `12:25:40` | `Product page A` |


If you want average time on site for the dimension item `Product page A`, first take the amount of time lapsed between hits for that dimension:

* **12:04:20 - 12:05:30** - 1 分 10 秒
* **12:05:30 - 12:07:00** - 1 分 30 秒
* **12:07:40 - 12:08:10** - 30 秒
* **12:25:40 - ?** - 未包含

`Product page A` 的逗留总时间是 `00:03:10`。此访问中存在两个序列：第一个序列是针对两个连续值，第二个序列是在结账前。此访问的最后一个点击不是序列，因为它不包含结束时间戳。

`Product page A` 的网站平均逗留时间是 `00:01:35`。

## 网站平均逗留时间（秒）

“网站平均逗留时间（秒）”量度以整数的形式显示相同的数据，而不是 `HH:MM:SS` 格式。此量度是计算度量中最有价值的组成部分。

## 划分总数与父行项目不匹配

“网站平均逗留时间”量度使用给定维度的未中断序列。在计算这些序列时，划分维度不取决于父维度。例如，请考虑以下访问：

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Calculating average time on site for the dimension item `Home` would use the following calculation:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

如果您使用[网站区域](../dimensions/site-section.md)维度应用划分，则将使用以下计算方法：

```text
(30 + 10) / 1 = 40 seconds average time on site
```

由于划分维度中存在单个序列，因此它会使用与其父维度不同的分母。这些量度提供的结果通常在访问级别相似，但在点击级别可能不同。

## 百分比高于 100%

此量度通常包含高于 100% 的百分比。分母是整个维的站点平均时间，分子是维项的站点平均时间。 如果整个维度的站点平均时间低于给定维度项目的站点平均时间，您将看到高于100%的百分比。 按此量度对排名报表进行排序，会显示网站平均逗留时间的异常值，该值通常没什么价值。Adobe 建议在排名报表中按其他量度（例如[访问次数](visits.md)）来排序。

有关逗留时间的更多常规信息，请参阅[逗留时间概述](time-spent.md)。
