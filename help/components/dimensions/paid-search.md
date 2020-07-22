---
title: 付费搜索
description: 区分付费和自然搜索的指标。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# 付费搜索

通过“付费搜索”维度，您可以查看任何指标，并在付费搜索和自然搜索之间进行比较。 将忽略搜索引擎外的所有其他点击。 此维度有助于了解您的付费搜索工作与有机搜索的对比情况。

## 用数据填充此维

此维度正常工作的唯一要求是在报表包设 [置中正确配置](/help/admin/admin/paid-search-detection/paid-search-detection.md) “付费搜索检测”。 如果付费搜索检测配置正确且报表包包含数据，则此维度始终有效。

## 维项

维项包括两个静态值： `"Natural"` 和 `"Paid"`。 如果访问与搜索引擎的条件匹配且与付费搜索检测也匹配，则它属于维 `"Paid"` 度项。 如果访问与搜索引擎的条件匹配且与付 *费搜* 索检测不匹配，则它属于 `"Natural"` 维项。
