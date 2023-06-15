---
title: 实例
description: 设置了变量（且未保留）的点击数。
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 21029930b5cae6acb6bc6a59836ddc1ca33cb27e
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 65%

---

# 实例

“实例”量度显示在图像请求中明确定义维度的次数。某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留维度项目。当您希望查看维度项目设定的次数，但不包含保留该值的点击时，此量度非常有用。

## 如何计算此量度

在报表包的所有点击中，只包含在图像请求中显式设置维度项目的点击。某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留。[页面视图](page-views.md)和[发生次数](occurrences.md)等量度计算初始值和保留值。此量度不计算保留值。

例如，访客访问您的网站并使用内部搜索。 可在eVar1中跟踪内部搜索。 使用内部搜索一次后，他们会在离开之前再访问五个页面。

在工作区中查看报表时，您会看到一个eVar1实例和六次发生次数。 一个在搜索结果页面上触发的实例，而发生次数计算初始值和保留值。
