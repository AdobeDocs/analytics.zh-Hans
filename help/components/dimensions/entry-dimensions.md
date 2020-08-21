---
title: 登入维度
description: 列出登入维度及其使用情况。
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 58%

---


# 登入维度

*此帮助页介绍登入次数如何作为维度使用。有关登入次数如何作为量度使用的信息，请参阅[登入次数](../metrics/entries.md)量度。*

登入维度基于访问。他们记录第一个维度项目，并在访问的整个过程中保留该项目。 登入维度可用于在“报表包”设置中的[流量变量](/help/admin/admin/c-traffic-variables/traffic-var.md)下启用路径的所有变量。

## 使用数据填充登入维度

给定的登入维度基于其关联的流量变量。如果非登入变量包含数据，则其关联的登入维度也包含数据。如果流量变量包含数据，则不需要对登入维度进行更改。

## Dimension项

由于输入变量通常基于实施中的自定义字符串，因此您的组织将决定维项是什么。 给定条目维中的值与其关联的非条目维中的维度项匹配。 例如，“条目页面”维中的维项目包含“页面”维中的类似维项目。

## 原始登入页面

“原始登入页面”维度的操作方式与其他登入维度不同。它不保留给定访问的登入页面，而是保留该访客 Cookie 的整个生命周期中的第一个登入页面。For example, if you land on `https://example.com/page4` for your first visit to the site, then a year later land on `https://example.com/store`, The &#39;Entry page original&#39; dimension lists `https://example.com/page4` as the dimension item.
