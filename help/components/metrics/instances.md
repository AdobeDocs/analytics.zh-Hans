---
title: 实例
description: 设置了变量（且未保留）的点击数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 52%

---


# 实例

“实例”量度显示在图像请求中明确定义维度的次数。Some dimensions, such as [eVars](../dimensions/evar.md), persist dimension items past the hit they are set on. 当您希望查看维度项目设置次数时，该度量会很有用，而没有该值会持续存在的点击次数。

## 如何计算此量度

在报表包中的所有点击中，只包括在图像请求中显式设置维项的点击。 某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留。[页面视图](page-views.md)和[发生次数](occurrences.md)等量度计算初始值和保留值。此量度不计算保留值。