---
title: 服务器
description: 服务器的名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 85%

---


# 服务器

“服务器”维度通常列出站点的主机名。对于组合多个域或子域的报表包，当想要了解哪些域或子域的性能最佳时，此维度很有价值。

此维度与[页面](page.md)维度和[网站区域](site-section.md)维度相关。页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维度从图像请求中的 [`server` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用 [`server`](/help/implement/vars/page-vars/server.md) 变量收集此数据。

## Dimension项

Dimension项包括站点上的服务器。 您的组织确定要使用哪些特定维项目。 有些组织使用 `window.location.hostname`，而另一些组织则制定自定义值。无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。
