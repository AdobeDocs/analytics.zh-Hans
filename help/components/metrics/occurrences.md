---
title: 发生次数
description: 设置或保留变量的点击次数。
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 64%

---

# 发生次数

“发生次数” [量度](overview.md) 显示设置或保留给定维度的点击数。 将工作区中的维度拖至空白画布时，Adobe 会自动将此量度应用于项目。

## 如何计算此量度

在报表包的所有点击中，包括定义或保留维度项目的点击。某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留。此量度计算初始值和保留值。

## 与类似量度比较

* **发生次数与[实例](instances.md)**：发生次数计算设置或保留维度项目的点击次数。实例不包括保留维度项目的点击。
* **发生次数与 [页面查看次数](page-views.md)**：发生次数包括所有点击类型，包括页面查看跟踪调用([`t()`](/help/implement/vars/functions/t-method.md))，链接跟踪调用([`tl()`](/help/implement/vars/functions/tl-method.md))，以及摘要中的数据 [数据源](/help/import/data-sources/overview.md). 页面查看次数量度仅包含页面查看跟踪调用，不包括链接跟踪调用和摘要数据源。
