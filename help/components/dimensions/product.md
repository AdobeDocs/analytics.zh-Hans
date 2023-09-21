---
title: 产品
description: 产品的名称。
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 91%

---

# 产品

“产品” [维度](overview.md) 报告点击中产品的名称。 此维度对于使用 `products` 变量且想要查看产品相关量度（例如，最畅销的产品或查看次数最多的产品）的实施非常有用。如果您的网站上没有任何产品，则此维度可能会特意留空。

## 使用数据填充此维度

此维度引用 [`products`](/help/implement/vars/page-vars/products.md) 变量中字符串的第二部分。第一个和第二个分号 (`;`) 之间的字符将填充此维度。

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。Adobe 建议为产品确立一致的命名约定。如果想对产品进行不同分组或为其提供更友好的名称，则可以使用[分类](../classifications/c-classifications.md)。Adobe 建议同时使用“产品”和“类别”维度。
