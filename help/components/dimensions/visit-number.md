---
title: 访问量
description: 访客的第 n 次访问。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 59%

---


# 访问量

“访问量”维度报告访客当前是第几次访问。当新访问开始时，此维度项增加1。 如果您想了解访客在返回您的网站时的参与程度，此维度很有用。它是一个基于访问的维度，这意味着它在整个访问期间包含的值是相同的，并且无法更改。它适用于访客的存留期，而不管项目日期范围如何。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## Dimension项

Dimension items include the string `"Visit number"` followed by the numeric representation of the visit the visitor is currently on. For example, if the visitor has never been to your site before, their first visit belongs to the dimension item `"Visit number 1"`. If this is the visitor&#39;s 13th visit to your site, they belong to the dimension item `"Visit number 13"`.
