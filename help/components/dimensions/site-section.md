---
title: 网站区域
description: 网站区域的名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 82%

---


# 网站区域

“网站区域”维度列出您的网站上网站区域的名称。对于大型网站，将页面分组到区域会很有帮助。此维度对于查看“查看次数最多”或“性能最高”网站区域很有帮助。

此维度与[页面](page.md)维度和[服务器](server.md)维度相关。页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维度从图像请求中的 [`ch` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用 [`channel`](/help/implement/vars/page-vars/channel.md) 变量收集此数据。

## Dimension项

Dimension项包括站点上的站点部分的名称。 您的组织确定要使用哪些特定维项目。 无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。
