---
title: 搜索引擎
description: 访客用来访问您的网站的搜索引擎。
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 93%

---

# 搜索引擎

“搜索引擎”[维度](overview.md)报告访客用来访问您的网站的搜索引擎。 反向链接必须满足以下两项要求才能分类为搜索引擎：

* Adobe 将反向链接域识别为有效的搜索引擎；
* 反向链接 URL 中存在关键词查询字符串参数。查询字符串参数可以为空（与由于隐私惯例而使用多个搜索引擎的情况一样）。

如果要区分付费和免费搜索，需要使用[付费搜索检测](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)。多个维度可用于搜索引擎：

* **搜索引擎**：用于访问您的网站的搜索引擎，无论是付费搜索引擎，还是免费搜索引擎。
* **搜索引擎 - 付费**：用于访问您的网站的搜索引擎，与付费搜索检测相匹配。
* **搜索引擎 - 免费**：用于访问您的网站的搜索引擎，与付费搜索检测不匹配。

## 使用数据填充此维度

此维度引用 Adobe 内部的多个查找表。每个值都基于点击的[反向链接](referrer.md)，具体取决于[内部 URL 过滤器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。确保正确配置反向链接维度和内部 URL 过滤器。

## 维度项目

维度项目包括用于访问您的网站的搜索引擎。示例值包括 `"Google"`、`"Microsoft Bing"` 和 `"DuckDuckGo"`。`"Unspecified"` 维度项目是指所有非搜索流量。
