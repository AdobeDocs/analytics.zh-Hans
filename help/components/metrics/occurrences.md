---
title: 发生次数
description: 设置或保留变量的点击次数。
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 0c5062363e10d9b545a3209ebaefcc6fa5d02c8b
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 57%

---

# 发生次数

“发生次数”[量度](overview.md)显示设置或持久化某个给定维度所经历的点击次数。将工作区中的维度拖至空白画布时，Adobe 会自动将此量度应用于项目。

## 如何计算此量度

在报表包的所有点击中，包括定义或保留维度项目的点击。某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留。此量度计算初始值和保留值。

## 与类似量度比较

* **发生次数与[实例](instances.md)**：发生次数计算设置或保留维度项目的点击次数。实例不包括保留维度项目的点击。
* **发生次数与[页面查看次数](page-views.md)**：发生次数包括所有点击类型，包括页面查看跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md))、链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 和摘要[数据源](/help/import/data-sources/overview.md)中的数据。页面查看次数量度仅包括页面查看跟踪调用，不包括链接跟踪调用和摘要数据源。

## 持久性

持久性表示给定的维度值能否在从中设置它的事件之外与指标相关。 它使用分配和到期的组合。 通过分配，可决定一次可在单个列中保留多个维度项时保留哪个值。 通过到期，可决定维度项目在从中设置它的事件之外保持多久。

持久性仅在维度上可用，并可追溯至应用该持久性的数据。 它是紧接应用筛选或其他分析操作之前发生的数据转换。 如果未启用持久性，则维度仅与同一事件中存在的量度相关。