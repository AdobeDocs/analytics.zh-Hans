---
description: Analytics 变量的长度会影响 HTML 代码段、JavaScript 库文件及图像请求的大小。
keywords: Analytics 实施
seo-description: Analytics 变量的长度会影响 HTML 代码段、JavaScript 库文件及图像请求的大小。
seo-title: 变量长度
solution: Analytics
subtopic: 故障诊断
title: 变量长度
topic: 开发人员和实施
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 变量长度

Analytics 变量的长度会影响 HTML 代码段、JavaScript 库文件及图像请求的大小。

如果客户采用多个较长（60 个字符或更多）的变量，则这些值可被替换为较短的标识符。利用数据分类或 VISTA 规则，可将这些标识符转换为易记的名称。

> [!NOTE]大部分 Analytics 变量的长度上限为 100 个字符（eVar 的上限为 255 个字符）。Internet Explorer 允许在 GET“图像请求”URL 中最多包含 2,048 个字符。上述图像请求限制不仅适用于变量，也适用于有关浏览器、操作系统及浏览器插件（仅限 Netscape/Mozilla）的信息。

