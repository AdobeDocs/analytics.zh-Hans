---
title: 发生次数
description: 设置或保留变量的点击次数。
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '153'
ht-degree: 100%

---


# 发生次数

“发生次数”量度显示设置或保留给定维度的点击次数。将工作区中的维度拖至空白画布时，Adobe 会自动将此量度应用于项目。

## 如何计算此量度

在报表包的所有点击中，包括定义或保留维度项目的点击。某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留。此量度计算初始值和保留值。

## 与类似量度比较

* **发生次数与[实例](instances.md)**：发生次数计算设置或保留维度项目的点击次数。实例不包括保留维度项目的点击。
* **发生次数与[页面查看次数](page-views.md)**：发生次数包括所有点击类型，包括页面查看跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md)) 和链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md))。页面查看次数量度仅包含页面查看跟踪调用，不包含链接跟踪调用。
