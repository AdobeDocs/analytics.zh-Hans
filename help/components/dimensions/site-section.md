---
title: 网站区域
description: 网站区域的名称。
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '137'
ht-degree: 100%

---

# 网站区域

“网站区域”维度列出您的网站上网站区域的名称。对于大型网站，将页面分组到区域会很有帮助。此维度对于查看“查看次数最多”或“性能最高”网站区域很有帮助。

此维度与[页面](page.md)维度和[服务器](server.md)维度相关。页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维度从图像请求中的 [`ch` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用 [`channel`](/help/implement/vars/page-vars/channel.md) 变量收集此数据。

## 维度项目

维度项目包括您网站上的网站区域的名称。贵组织会确定您要使用的具体维度项目。无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。
