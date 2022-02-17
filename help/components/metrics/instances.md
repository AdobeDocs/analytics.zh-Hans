---
title: 实例
description: 设置了变量（且未保留）的点击数。
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 100%

---

# 实例

“实例”量度显示在图像请求中明确定义维度的次数。某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留维度项目。当您希望查看维度项目设定的次数，但不包含保留该值的点击时，此量度非常有用。

## 如何计算此量度

在报表包的所有点击中，只包含在图像请求中显式设置维度项目的点击。某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留。[页面视图](page-views.md)和[发生次数](occurrences.md)等量度计算初始值和保留值。此量度不计算保留值。
