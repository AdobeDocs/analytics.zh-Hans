---
title: 浏览器类型
description: 开发浏览器的组织。
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 89%

---

# 浏览器类型

&#39;浏览器类型&#39; [维度](overview.md) 列出开发访客所用浏览器的组织。 如果您想要了解访客使用的主要浏览器，此维度非常有用。它提供了超过“浏览器”维度的价值，因为它不会将同一浏览器的不同版本列为单独的维度项目。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。

## 维度项目

维度项目包括开发浏览器的组织。常见的维度项目包括 `"Google"`（[!DNL Chrome] 的创建者）、`"Apple"`（[!DNL Safari] 的创建者）、`"Microsoft"`（[!DNL Edge] 的创建者）以及 `"Mozilla"`（[!DNL Firefox] 的创建者）。
