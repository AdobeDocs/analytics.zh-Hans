---
title: 搜索引擎
description: 访客用来访问您的网站的搜索引擎。
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 69%
---
# 搜索引擎

“搜索引擎”[维度](overview.md)报告访客用来访问您的网站的搜索引擎。 反向链接必须满足以下两项要求才能分类为搜索引擎：

* Adobe 将反向链接域识别为有效的搜索引擎；
* 反向链接 URL 中存在关键词查询字符串参数。 查询字符串参数可以为空（由于隐私惯例，多个搜索引擎都是这种情况）。

如果要区分付费和免费搜索，需要使用[付费搜索检测](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)。 多个维度可用于搜索引擎：

* **搜索引擎**：用于访问您的网站的搜索引擎，无论是付费搜索引擎，还是免费搜索引擎。
* **搜索引擎 - 付费**：用于访问您的网站的搜索引擎，与付费搜索检测相匹配。
* **搜索引擎 - 免费**：用于访问您的网站的搜索引擎，与付费搜索检测不匹配。

## 使用数据填充此维度

Adobe从每次点击的[反向链接](referrer.md)派生此维度，并将其与Adobe内部的多个查找表进行匹配。 没有要设置的变量。 由于每个值都依赖于反向链接，因此请确保正确配置了反向链接维度和[内部URL过滤器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自反向链接） |
| **Web SDK / XDM字段** | 无（派生自反向链接） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

## 维度项目

维度项目包括访客用来访问您的网站的搜索引擎。 示例值包括 `"Google"`、`"Microsoft Bing"` 和 `"DuckDuckGo"`。 `"Unspecified"` 维度项目是指所有非搜索流量。
