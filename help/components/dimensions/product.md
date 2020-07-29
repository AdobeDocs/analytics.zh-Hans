---
title: 产品
description: 产品的名称。
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# 产品

“产品”维报告点击中产品的名称。 它对于使用变量并希望查看产品 `products` 相关指标（如最畅销商或最常查看的商品）的实施很有用。 如果您的站点上没有任何产品，则此维度可能有意为空。

## 用数据填充此维

该维引用变量中字符串的第二部分 [`products`](/help/implement/vars/page-vars/products.md) 。 第一个和第二个分号()之间的字`;`符填充此维。

## Dimension项

由于此变量基于实施中的自定义字符串，因此您的组织将确定维项目。 Adobe建议您为产品建立一致的命名约定。 [如果要以](../classifications/c-classifications.md) 其他方式对产品进行分组或提供更友好的名称，可使用分类。 Adobe建议同时使用“产品”和“类别”维。
