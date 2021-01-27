---
title: 退出链接
description: 退出链接的名称。
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 54%

---


# 退出链接

“退出链接”维度报告在您的站点上实现的退出链接的名称。 当您想要了解哪些链接最常用于指向网站外的域时，此维度很有价值。

## 使用数据填充此维度

此维度从图像请求中的 [`pev2` 查询字符串](/help/implement/validate/query-parameters.md) 为还具有值为 `lnk_e` 的 `pe` 查询字符串的点击收集数据。如果 `pe` 查询字符串在点击中具有不同的值，则此维度不会收集数据。

如果要使用AppMeasurement将数据发送到此维，请发送一个[`tl()`](/help/implement/vars/functions/tl-method.md)图像请求，其链接类型参数为`"e"`。 用所需值填充链接名称参数。

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。Adobe 建议您根据报表需求将链接分组为有意义的类别。
