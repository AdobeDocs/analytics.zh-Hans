---
title: 操作系统类型
description: 操作系统，不考虑版本。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 53%

---

# 操作系统类型

“操作系统类型”[维度](overview.md)显示访客使用的总体操作系统，而不考虑特定版本。 此维度不仅有助于了解最常用的特定操作系统和版本，而且还有助于了解访客使用的典型操作系统平台。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。Adobe与[DeviceAtlas](https://deviceatlas.com/)合作，以在User Agent和操作系统类型之间维护查找。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans)时启用[!UICONTROL 设备查找]。

## 维度项

Dimension项目包括使用的操作系统类型。 示例包括 `"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"` 和 `"Apple iOS"`。
