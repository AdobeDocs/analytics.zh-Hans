---
title: 自定义链接
description: 自定义链接的名称。
translation-type: ht
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: ht
source-wordcount: '152'
ht-degree: 100%

---


# 自定义链接

“自定义链接”维度报告在网站上实施的自定义链接的名称。当您想要了解访客点击次数最多的链接类型时，此维度很有价值。

## 使用数据填充此维度

此维度从图像请求中的 [`pev2` 查询字符串](/help/implement/validate/query-parameters.md)为还具有值为 `lnk_o` 的 `pe` 查询字符串的点击收集数据。如果 `pe` 查询字符串在点击中具有不同的值，则此维度不会收集数据。

如果要使用 AppMeasurement 将数据发送到此维度，请发送一个 [`tl()`](/help/implement/vars/functions/tl-method.md) 图像请求，其链接类型参数为 `"o"`。使用所需的值填充链接名称参数。

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。Adobe 建议您根据报表需求将链接分组为有意义的类别。
