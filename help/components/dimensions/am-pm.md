---
title: 上午/下午
description: 确定在上午还是下午小时中是否发生了点击。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---


# 上午/下午

“AM/PM”维度提供有关在AM或PM小时内是否发生点击的分析。 The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## 用数据填充此维

此尺寸不会变。 它没有任何要更改的设置。 它的唯一依赖关系是报表包的时区，它决定哪些小时是AM和哪些是PM。

## 维项

此维始终仅包含两个维项： `"AM"` 和 `"PM"`。 维项目适 `"AM"` 用于从上午12:00到上午11:59的所有点击，而维项目 `"PM"` 适用于下午12:00到下午11:59的所有点击。
