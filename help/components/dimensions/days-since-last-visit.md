---
title: 上次访问间隔天数
description: 当前点击与上次访问之间间隔的天数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 74%

---


# 上次访问间隔天数

“上次访问间隔天数”维度会测量访客的当前点击与其上次访问（如果有）之间间隔的时间。此维度有助于您了解访客在访问您的网站后的行为。示例包括：

* 用户回访网站的频率是多久？
* 回访频度与转化有何关联？重复购买者是否经常访问？
* 点击促销活动的用户是否经常回访？

此维度中不包含首次访客。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## Dimension项

Dimension项包括访客上次访问与当前点击之间的天数。 Each number of days is a separate dimension item, with `"Same day"` occurring where a visitor&#39;s last visit and the current hit happened on the same day.
