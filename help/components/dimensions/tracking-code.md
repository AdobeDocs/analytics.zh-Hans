---
title: 跟踪代码
description: 跟踪代码或活动的名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 3%

---


# 跟踪代码

“跟踪代码”维度列表站点上跟踪代码的名称。 此维通常使用查询字符串参数收集。 您可以将具有不同查询字符串参数值的链接放置在Internet上的不同位置。 此维度报告哪些链接在驱动网站流量方面最为成功。

## 用数据填充此维

此维从图像请求中的 [`v0` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用变量收集此 [`campaign`](/help/implement/vars/page-vars/campaign.md) 数据。

## 维项

维项目包括站点上跟踪代码的名称。 您的组织确定要使用哪些特定维项目。
