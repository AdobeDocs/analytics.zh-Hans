---
title: 发生次数
description: 设置或保留变量的点击数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 1%

---


# 发生次数

“发生次数”度量显示设置或保留给定维度的点击次数。 将Workspace中的维拖至空白画布时，Adobe会自动将此度量应用于项目。

## 如何计算此度量

在报表包中的所有点击中，包括定义或保留维项的点击。 某些维度(如 [eVar](../dimensions/evar.md))在设置的点击之外仍然有效。 页面视图 [和发生](page-views.md) 等 [度量](occurrences.md) 计算初始值和保留值。 此度量不计算持久值。

## 与类似指标比较

* **发生次数与[实例](instances.md)**: 在设置或保留维项目时，发生次数会计点击次数。 实例不包括维项持续存在的点击。
* **发生次数与页[面视图](page-views.md)**: 发生次数包括所有点击类型，包括页面视图跟[`t()`](/help/implement/vars/functions/t-method.md)踪调用()和链接跟踪调[`tl()`](/help/implement/vars/functions/tl-method.md)用()。 页面视图量度仅包括页面视图跟踪调用，并不包括链接跟踪调用。