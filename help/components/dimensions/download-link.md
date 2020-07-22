---
title: 下载链接
description: 下载链接的名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 17%

---


# 下载链接

“下载链接”维度报告网站上实现的下载链接的名称。 当您想要了解有关下载链接的访客行为的更多信息时，此维度很有价值，例如：

* 确定您网站中下载最频繁的文件。
* 了解某些文件在特定时段内下载的次数是否更多。
* 验证访客是否下载不同的文件类型（如果提供）。

## 用数据填充此维

该维从图像请求中 [`pev2` 的查询字符串](/help/implement/validate/query-parameters.md) (对于具有值为的字符串 `pe` ，该查询字符串也包含字符串)收集数据 `lnk_d`。 如果查询 `pe` 字符串在点击中具有不同的值，则此维不会收集数据。

如果要使用AppMeasurement将数据发送到此维：

* 用所需 [`linkName`](/help/implement/vars/config-vars/linkname.md) 的值填充变量。
* 将 [`linkType`](/help/implement/vars/config-vars/linktype.md) 变量设置为 `"d"`.
* 发送图 [`tl()`](/help/implement/vars/functions/tl-method.md) 像请求。

## 维项

由于此变量基于实施中的自定义字符串，因此您的组织将确定维项目。 Adobe建议您根据类别需求将链接分组到有意义的报告中。
