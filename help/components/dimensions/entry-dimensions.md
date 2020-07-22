---
title: 条目维
description: 列表条目维及其使用。
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# 条目维

*此帮助页描述了条目作为维的工作方式。 有关条目如何作为度量的信息，请参[阅条目](../metrics/entries.md)度量。*

入口维度基于访问。 他们记录第一个维度项目，并在访问的整个过程中保留该项目。 条目维度可用于在“报表包”设置中的“流量变量”下启 [用寻路](/help/admin/admin/c-traffic-variables/traffic-var.md) 的所有变量。

## 用数据填充条目维

给定的输入维度基于其关联的流量变量。 如果非条目变量包含数据，则其关联的条目维也包含数据。 如果流量变量包含数据，则输入维不需要实施更改。

## 维项

由于输入变量通常基于实施中的自定义字符串，因此您的组织将决定维项是什么。 给定条目维中的值与其关联的非条目维中的维度项匹配。 例如，“条目页面”维中的维项目包含“页面”维中的类似维项目。

## 输入页面原始

“条目页面原始”维的操作方式与其他条目维不同。 它不是保留给定访问的进入页面，而是保留该访客cookie的整个生命周期中的第一个进入页面。 例如，如果您首次登 `https://example.com/page4` 陆网站，一年后登陆，“登入页面原始” `https://example.com/store`维度列表作为维 `https://example.com/page4` 度项目。
