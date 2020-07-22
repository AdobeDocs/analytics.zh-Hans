---
title: 所有搜索页面排名
description: 确定访客点击到您网站的搜索引擎上的哪个页面。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# 所有搜索页面排名

“所有搜索页面排名”维度可以分析访客点击了您的站点的搜索结果页面。 例如，如果您的站点显示在搜索引擎搜索结果的第二页上，则此变量的维项为“搜索页2”。

## 用数据填充此维

要使此维度仅正常工作，您的报表包必须 [正确设置内部](/help/admin/admin/internal-url-filter-admin.md) URL过滤器。 AppMeasurement可自动填充此维，而不会更改任何实施代码。

## 维项

如果访客从搜索引擎点进到您的站点，则此维度的值为“搜索页面”，后跟他们点进的页码。 如果点击不是源自搜索引擎，则此维的值为“未指定”。
