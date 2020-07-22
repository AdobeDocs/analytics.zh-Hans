---
title: 类别
description: 点击的产品类别。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---


# 类别

“类别”维度报告点击的产品类别。 它对于使用变量并希望查看产品类别 `products` 相关指标（如最畅销商或查看次数最多的商家）的实施非常有用。 如果您的站点上没有任何产品，则此维度可能有意为空。

## 用数据填充此维

该维引用变量中字符串的第一部 [`products`](/help/implement/vars/page-vars/products.md) 分。 第一个分号()之前的所`;`有内容都填充此维。

## 维项

由于此变量基于实施中的自定义字符串，因此您的组织将确定维项目。 Adobe建议您使用“产品”和“类别”维度将各个产品分组为有意义的类别。

>[!TIP]
>
>在以前版本的AdobeAnalytics中，“类别”维度由于其处理架构而受到一些限制。 这些限制现已删除，允许您使用任何指标和任何细分。
