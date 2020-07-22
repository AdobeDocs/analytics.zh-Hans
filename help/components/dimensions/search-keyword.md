---
title: 搜索关键字
description: 访客用来访问您的站点的搜索关键字。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# 搜索关键字

“搜索关键字”维度报告访客用于访问您的站点的搜索关键字。

>[!IMPORTANT]
>
>由于隐私惯例不断增加，大多数搜索引擎不再传递搜索关键字。 Adobe识别搜索引擎但在维项目下缺少关键字组的点击 `"Keyword unavailable"`。

推荐人必须满足以下两项才能分类为搜索关键字：

* Adobe将引用域识别为有效的搜 [索引擎](search-engine.md);
* 引用URL中存在关键字查询字符串参数。 如果关键字查询字符串存在但不包含值，则它会在维项下进行分组 `"Keyword unavailable"`。

如果要区分付费和自然搜索，则需 [要“付费搜索](/help/admin/admin/paid-search-detection/paid-search-detection.md) ”检测。 多个维可用于搜索关键字：

* **搜索关键字**: 用于访问网站的搜索关键字，无论其是付费还是自然。
* **搜索关键字——付费**: 用于访问网站的搜索关键字与付费搜索检测相匹配。
* **搜索关键字——自然**: 用于访问您的站点的搜索关键字，与付费搜索检测不匹配。

## 用数据填充此维

此维引用Adobe内部的多个查找表。 每个值都基于点击 [的推荐人](referrer.md) ，这取决于 [内部URL过滤器](/help/admin/admin/internal-url-filter-admin.md)。 确保正确配置推荐人维和内部URL过滤器。

## 维项

维度项目包括用于访问站点的搜索关键字。 维 `"Unspecified"` 度项是所有非搜索流量。
