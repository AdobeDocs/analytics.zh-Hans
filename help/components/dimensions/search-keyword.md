---
title: 搜索关键词
description: 访客用来访问您的网站的搜索关键词。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 78%

---


# 搜索关键词

“搜索关键词”维度报告访客用于访问您的网站的搜索关键词。

>[!IMPORTANT]
>
>由于隐私条例不断增加，大多数搜索引擎不再传递搜索关键词。Hits where Adobe recognizes a search engine but is missing a keyword groups under the dimension item `"Keyword unavailable"`.

反向链接必须满足以下两项才能分类为搜索关键词：

* Adobe 将反向链接域识别为有效的[搜索引擎](search-engine.md)；
* 反向链接 URL 中存在关键词查询字符串参数。If the keyword query string exists but does not contain a value, it groups under the dimension item `"Keyword unavailable"`.

如果要区分付费和免费搜索，需要使用[付费搜索检测](/help/admin/admin/paid-search-detection/paid-search-detection.md)。有多个维度可用于搜索关键词：

* **搜索关键词**：用于访问网站的搜索关键词，无论是付费搜索还是免费搜索。
* **搜索关键词 - 付费**：用于访问网站的搜索关键词，与付费搜索检测相匹配。
* **搜索关键词 - 免费**：用于访问网站的搜索关键词，与付费搜索检测不匹配。

## 使用数据填充此维度

此维度引用 Adobe 内部的多个查找表。每个值都基于点击的[反向链接](referrer.md)，具体取决于[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)。确保正确配置反向链接维度和内部 URL 过滤器。

## Dimension项

Dimension项包括用于访问您的站点的搜索关键字。 The `"Unspecified"` dimension item is all non-search traffic.
