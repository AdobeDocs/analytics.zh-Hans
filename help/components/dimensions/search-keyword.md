---
title: 搜索关键词
description: 访客用来访问您的网站的搜索关键词。
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 94%

---

# 搜索关键词

“搜索关键词”[维度](overview.md)报告访客用来访问您的网站的搜索关键词。

>[!IMPORTANT]
>
>由于隐私条例不断增加，大多数搜索引擎不再传递搜索关键词。Adobe 识别搜索引擎但缺少关键词的点击将分组到维度项目 `"Keyword unavailable"` 下。

反向链接必须满足以下两项才能分类为搜索关键词：

* Adobe 将反向链接域识别为有效的[搜索引擎](search-engine.md)；
* 反向链接 URL 中存在关键词查询字符串参数。如果关键词查询字符串存在但不包含值，则它将分组到维度项目 `"Keyword unavailable"` 下。

如果要区分付费和免费搜索，需要使用[付费搜索检测](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)。有多个维度可用于搜索关键词：

* **搜索关键词**：用于访问网站的搜索关键词，无论是付费搜索还是免费搜索。
* **搜索关键词 - 付费**：用于访问网站的搜索关键词，与付费搜索检测相匹配。
* **搜索关键词 - 免费**：用于访问网站的搜索关键词，与付费搜索检测不匹配。

## 使用数据填充此维度

此维度引用 Adobe 内部的多个查找表。每个值都基于点击的[反向链接](referrer.md)，具体取决于[内部 URL 过滤器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。确保正确配置反向链接维度和内部 URL 过滤器。

## 维度项目

维度项目包括用于访问您的网站的搜索关键词。`"Unspecified"` 维度项目是指所有非搜索流量。
