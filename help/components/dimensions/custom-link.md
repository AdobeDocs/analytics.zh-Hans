---
title: 自定义链接
description: 自定义链接的名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 2%

---


# 自定义链接

“自定义链接”维报告在您的站点上实现的自定义链接的名称。 当您想了解访客点击次数最多的链接类型时，此维度很有价值。

## 用数据填充此维

该维从图像请求中 [`pev2` 的查询字符串](/help/implement/validate/query-parameters.md) (对于具有值为的字符串 `pe` ，该查询字符串也包含字符串)收集数据 `lnk_o`。 如果查询 `pe` 字符串在点击中具有不同的值，则此维不会收集数据。

如果要使用AppMeasurement将数据发送到此维：

* 用所需 [`linkName`](/help/implement/vars/config-vars/linkname.md) 的值填充变量。
* 将 [`linkType`](/help/implement/vars/config-vars/linktype.md) 变量设置为 `"o"`.
* 发送图 [`tl()`](/help/implement/vars/functions/tl-method.md) 像请求。

## 维项

由于此变量基于实施中的自定义字符串，因此您的组织将确定维项目。 Adobe建议您根据类别需求将链接分组到有意义的报告中。
