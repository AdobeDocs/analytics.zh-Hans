---
title: 单次存取
description: 维度项目在访问中未更改的次数。
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 93%

---

# 单次存取

“单次存取”量度[量度](overview.md)显示维度项目在整个访问期间仅包含单个唯一值的访问次数。 当您想要了解访问过程中哪个维度项目停滞不变时，此量度非常有用。

## 如何计算此量度

此量度会计算维度项目中包含单个唯一值的访问数量。您可以多次设置维度项目，或者让维度项目保持不变并仍计数为单次存取。一旦维度项目变为第二个唯一值，访问就不再计为单次存取。

## “单次存取”与“单个页面访问次数”的区别

在[页面](../dimensions/page.md)维度的上下文语境下，“单次存取”与“单页面访问量”完全相同。当您使用其他维度时，二者的差异就会显现。

* **单次存取**：显示给定维度项目在整个访问期间未更改的访问次数。它与您在项目中使用的维度息息相关。
* **单个页面访问次数**：显示“页面”维度在整个访问期间未更改的访问次数。即使您在报表中使用其他维度，它仍会计算包含单个唯一“页面”维度项目的访问量。

例如，请考虑以下两个点击访问的示例。报表中的维度为[网站部分](../dimensions/site-section.md)。

* 访客点击了两个页面，但它们都位于同一网站部分。由于网站部分在访问期间保持不变，因此它被计为“单次存取”。它不计为一次“单个页面访问”，因为访问包含多个唯一的“页面”维度项目。
* 访客点击不同网站区域中的两个页面，但两个页面的名称恰好相同。访问不计为“单次存取”，因为存在两个唯一的站点部分值。它计为一次“单个页面访问”，因为有一个唯一的“页面”维度项目。
