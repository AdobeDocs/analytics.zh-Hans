---
title: 产品
description: 产品的名称。
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 91%

---

# 产品

“产品”[维度](overview.md)报告点击中产品的名称。 此维度对于使用 `products` 变量且想要查看产品相关量度（例如，最畅销的产品或查看次数最多的产品）的实施非常有用。 如果您的网站上没有任何产品，则此维度可能会特意留空。

## 使用数据填充此维度

此维度引用 [`products`](/help/implement/vars/page-vars/products.md) 变量中字符串的第二部分。 第一个和第二个分号 (`;`) 之间的字符将填充此维度。

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。 Adobe 建议为产品确立一致的命名约定。 如果想对产品进行不同分组或为其提供更友好的名称，则可以使用[分类](../classifications/classifications-overview.md)。 Adobe 建议同时使用“产品”和“类别”维度。
