---
title: 搜索引擎
description: 访客用来访问您的网站的搜索引擎。
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 93%

---

# 搜索引擎

“搜索引擎”[维度](overview.md)报告访客用来访问您的网站的搜索引擎。 反向链接必须满足以下两项要求才能分类为搜索引擎：

* Adobe 将反向链接域识别为有效的搜索引擎；
* 反向链接 URL 中存在关键词查询字符串参数。 查询字符串参数可以为空（与由于隐私惯例而使用多个搜索引擎的情况一样）。

如果要区分付费和免费搜索，需要使用[付费搜索检测](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)。 多个维度可用于搜索引擎：

* **搜索引擎**：用于访问您的网站的搜索引擎，无论是付费搜索引擎，还是免费搜索引擎。
* **搜索引擎 - 付费**：用于访问您的网站的搜索引擎，与付费搜索检测相匹配。
* **搜索引擎 - 免费**：用于访问您的网站的搜索引擎，与付费搜索检测不匹配。

## 使用数据填充此维度

此维度引用 Adobe 内部的多个查找表。 每个值都基于点击的[反向链接](referrer.md)，具体取决于[内部 URL 过滤器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)。 确保正确配置反向链接维度和内部 URL 过滤器。

## 维度项目

维度项目包括用于访问您的网站的搜索引擎。 示例值包括 `"Google"`、`"Microsoft Bing"` 和 `"DuckDuckGo"`。 `"Unspecified"` 维度项目是指所有非搜索流量。
