---
title: 浏览器
description: 使用的浏览器的名称和版本。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '177'
ht-degree: 100%

---


# 浏览器

“浏览器”维度报告发送点击的浏览器的名称和版本。此维度有助于了解访客最常使用的浏览器。测试网站的新版本时，您可以在此维度中的热门浏览器上运行这些测试，以便最大限度地做好质量控制工作。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform Launch），则此维度可开箱即用。

## 维度项目

维度项目包括使用的浏览器名称和版本。同一浏览器的不同版本是不同的维度项目。

某些维度项目包含 `"(unknown version)"`，而不是版本号。此维度项目会引用 Adobe 尚未添加到其查找表的最新浏览器版本。由于浏览器经常更新，因此给定浏览器的 `"(unknown version)"` 很常见，而且是临时的。Adobe 通常在月度维护版本发布期间更新查找表。
