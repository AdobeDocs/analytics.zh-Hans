---
title: 浏览器
description: 使用的浏览器的名称和版本。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 206df584deab5f6f9b8eeb09d9c8ad4983424eea
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 58%

---

# 浏览器

“[!UICONTROL 浏览器]”[维度](overview.md)报告发送点击的浏览器的名称和版本。 当您想要测量访客最常使用的浏览器时，此维度很有用。 测试网站的新版本时，您可以在此维度中的热门浏览器上运行这些测试，以便最大限度地做好质量控制工作。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。Adobe与[DeviceAtlas](https://deviceatlas.com/)合作，以在User Agent与Browser之间维护查找。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)时启用[!UICONTROL 设备查找]。

## 维度项目

维度项目包括使用的浏览器名称和版本。同一浏览器的不同版本是不同的维度项目。

某些维度项目包含 `"(unknown version)"`，而不是版本号。此维度项目引用Adobe尚未添加到其查找表的最新浏览器版本。 由于浏览器经常更新，因此给定浏览器的 `"(unknown version)"` 很常见，而且是临时的。Adobe 通常在月度维护版本发布期间更新查找表。