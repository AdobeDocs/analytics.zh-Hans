---
title: 付费搜索
description: 从付费搜索与免费搜索方面区分量度。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---


# 付费搜索

通过“付费搜索”维度，您可以查看任何量度，并在付费搜索与免费搜索之间进行比较。搜索引擎以外的所有其他点击将会被忽略。此维度有助于您了解付费搜索与免费搜索的对比情况。

## 使用数据填充此维度

此维度正常使用的唯一要求是：在报表包设置中正确配置[付费搜索检测](/help/admin/admin/paid-search-detection/paid-search-detection.md)。如果付费搜索检测配置正确且报表包包含数据，则此维度始终有效。

## 维度项目

维度项目包括两个静态值：`"Natural"` 和 `"Paid"`。如果访问与搜索引擎的条件匹配并且与付费搜索检测也匹配，则它属于 `"Paid"` 维度项目。如果访问与搜索引擎的条件匹配但与付费搜索检测&#x200B;*不*&#x200B;匹配，则它属于 `"Natural"` 维度项目。
