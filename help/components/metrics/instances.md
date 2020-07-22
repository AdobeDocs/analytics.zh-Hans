---
title: 实例
description: 设置（且未保留）变量的点击数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# 实例

“实例”度量显示在图像请求中显式定义维的次数。 某些维(如eVar [](../dimensions/evar.md))会将维项保留到设置的点击之后。 当您希望查看维度项目设置次数时，该度量会很有用，而没有该值会持续存在的点击次数。

## 如何计算此度量

在报表包中的所有点击中，只包括在图像请求中显式设置维项的点击。 某些维度(如 [eVar](../dimensions/evar.md))在设置的点击之外仍然有效。 页面视图 [和发生](page-views.md) 等 [度量](occurrences.md) 计算初始值和保留值。 此度量不计算持久值。