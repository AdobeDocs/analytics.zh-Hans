---
title: 发生次数
description: 设置或保留变量的点击次数。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 67%

---


# 发生次数

“发生次数”量度显示设置或保留给定维度的点击次数。将工作区中的维度拖至空白画布时，Adobe 会自动将此量度应用于项目。

## 如何计算此量度

在报表包中的所有点击中，包括定义或保留维项的点击。 某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留。此度量计算初始值和持久值。

## 与类似量度比较

* **发生次数与[实例](instances.md)**:在设置或保留维项目时，发生次数会计点击次数。 实例不包括维项持续存在的点击。
* **发生次数与[页面查看次数](page-views.md)**：发生次数包括所有点击类型，包括页面查看跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md)) 和链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md))。页面查看次数量度仅包含页面查看跟踪调用，不包含链接跟踪调用。
