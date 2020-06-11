---
title: 实例
description: 设置（且未保留）变量的点击数。
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# 实例

“实例”度量显示在图像请求中显式定义维的次数。 某些维(如 [eVar](../dimensions/evar.md))会保留设置的点击后的维值。 当您希望查看设置维度值的次数时（没有该值保留的点击次数），此度量很有用。

## 如何计算此度量

在报表包中的所有点击中，只包括在图像请求中显式设置维值的点击。 某些维度(如 [eVar](../dimensions/evar.md))在设置的点击之外仍然有效。 页面视图 [和发生](page-views.md) 等 [度量](occurrences.md) 计算初始值和保留值。 此度量不计算持久值。