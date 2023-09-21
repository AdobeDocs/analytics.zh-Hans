---
title: 服务器
description: 服务器的名称。
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 92%

---

# 服务器

“服务器” [维度](overview.md) 通常会列出站点的主机名。 对于组合多个域或子域的报表包，当想要了解哪些域或子域的性能最佳时，此维度很有价值。

此维度与[页面](page.md)维度和[网站区域](site-section.md)维度相关。页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维度从图像请求中的 [`server` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用 [`server`](/help/implement/vars/page-vars/server.md) 变量收集此数据。

## 维度项目

维度项目包括您网站上的服务器。贵组织会确定您要使用的具体维度项目。有些组织使用 `window.location.hostname`，而另一些组织则制定自定义值。无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。
