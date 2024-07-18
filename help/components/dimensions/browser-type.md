---
title: 浏览器类型
description: 开发浏览器的组织。
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 67%

---

# 浏览器类型

“浏览器类型”[维度](overview.md)列出了制作访客所用浏览器的组织。 如果您想要了解访客使用的主要浏览器，此维度非常有用。它提供了超过“浏览器”维度的价值，因为它不会将同一浏览器的不同版本列为单独的维度项目。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。Adobe与[DeviceAtlas](https://deviceatlas.com/)合作，以在User Agent与Browser之间维护查找。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)时启用[!UICONTROL 设备查找]。

## 维度项目

维度项目包括开发浏览器的组织。常见的维度项目包括 `"Google"`（[!DNL Chrome] 的创建者）、`"Apple"`（[!DNL Safari] 的创建者）、`"Microsoft"`（[!DNL Edge] 的创建者）以及 `"Mozilla"`（[!DNL Firefox] 的创建者）。
