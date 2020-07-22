---
title: 搜索引擎
description: 访客用来访问您网站的搜索引擎。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---


# 搜索引擎

“搜索引擎”维度报告访客用来访问您网站的搜索引擎。 推荐人必须满足以下两项才能分类为搜索引擎：

* 引用域被Adobe识别为有效的搜索引擎；
* 引用URL中存在关键字查询字符串参数。 查询字符串参数可以为空（与由于隐私惯例而使用多个搜索引擎的情况一样）。

如果要区分付费和自然搜索，则需 [要“付费搜索](/help/admin/admin/paid-search-detection/paid-search-detection.md) ”检测。 多个维度可用于搜索引擎：

* **搜索引擎**: 用于访问您的网站的搜索引擎，无论其是付费还是自然。
* **搜索引擎——付费**: 用于访问您的网站的搜索引擎，与付费搜索检测相匹配。
* **搜索引擎——自然**: 用于访问您的网站的搜索引擎，与付费搜索检测不匹配。

## 用数据填充此维

此维引用Adobe内部的多个查找表。 每个值都基于点击 [的推荐人](referrer.md) ，这取决于 [内部URL过滤器](/help/admin/admin/internal-url-filter-admin.md)。 确保正确配置推荐人维和内部URL过滤器。

## 维项

维度项目包括用于访问您的站点的搜索引擎。 示例值 `"Google"`包括 `"Microsoft Bing"`、和 `"DuckDuckGo"`。 维 `"Unspecified"` 度项是所有非搜索流量。
