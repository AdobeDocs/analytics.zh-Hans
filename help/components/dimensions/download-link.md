---
title: 下载链接
description: 下载链接的名称。
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '184'
ht-degree: 100%

---

# 下载链接

“下载链接”维度报告网站上实现的下载链接的名称。当您想要了解有关下载链接的访客行为的更多信息时，此维度很有价值，例如：

* 确定您网站中下载最频繁的文件。
* 了解某些文件在特定时段内下载的次数是否更多。
* 验证是否已提供访客下载的不同文件类型。

## 使用数据填充此维度

此维度从图像请求中的 [`pev2` 查询字符串](/help/implement/validate/query-parameters.md)为还具有值为 `lnk_d` 的 `pe` 查询字符串的点击收集数据。如果 `pe` 查询字符串在点击中具有不同的值，则此维度不会收集数据。

如果要使用 AppMeasurement 将数据发送到此维度，请发送一个 [`tl()`](/help/implement/vars/functions/tl-method.md) 图像请求，其链接类型参数为 `"d"`。使用所需的值填充链接名称参数。

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。Adobe 建议您根据报表需求将链接分组为有意义的类别。
