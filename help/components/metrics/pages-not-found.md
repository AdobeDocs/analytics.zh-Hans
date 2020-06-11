---
title: 页面未找到
description: 包含错误的点击数。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 5%

---


# 页面未找到

*此帮助页介绍“找不到页面”如何作为度量。 有关详[细信息，请参](../dimensions/pages-not-found.md)阅“找不到页面”维。*

“找不到页面”度量显示页面包含错误的点击次数。 当您想要查看哪些页面或URL包含错误消息（如404）时，此度量很有价值，因此您可以确定错误的原因并进行修复。

## 如何计算此度量

此度量计算变量等 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 于值的所有命中 `"errorPage"`。 它是“找不到页面”维 [度的等效度量](../dimensions/pages-not-found.md) 。