---
title: 所有搜索页面排名
description: 确定访客点击了搜索引擎上的哪个页面进入您的网站。
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '145'
ht-degree: 100%

---


# 所有搜索页面排名

“所有搜索页面排名”维度可以提供有关访客点击了搜索结果的哪个页面进入您网站的分析。例如，如果您的网站出现在搜索引擎的搜索结果的第二页，则此变量的维度项目是“搜索页面 2”。

## 使用数据填充此维度

要使此维度正常工作，只需为您的报表包正确设置[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)。AppMeasurement 会自动填充此维度，而无需更改任何实施代码。

## 维度项目

如果访客从搜索引擎点击进入您的网站，则此维度的值为“搜索页面”，后跟他们点击的页码。如果点击不是来自搜索引擎，则此维度的值为“未指定”。
