---
description: Analytics 变量的长度会影响 HTML 代码段、JavaScript 库文件及图像请求的大小。
keywords: Analytics 实施
seo-description: Analytics 变量的长度会影响 HTML 代码段、JavaScript 库文件及图像请求的大小。
seo-title: 可变长度
solution: Analytics
subtopic: 故障诊断
title: 可变长度
topic: 开发人员和实施
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 可变长度

Analytics 变量的长度会影响 HTML 代码段、JavaScript 库文件及图像请求的大小。

如果客户采用多个较长（60 个字符或更多）的变量，则这些值可被替换为较短的标识符。利用数据分类或 VISTA 规则，可将这些标识符转换为易记的名称。

>[!NOTE]
>
>大多数Analytics变量最多具有100个字符(eVar最多为255个字符)。Internet Explorer 允许在 GET“图像请求”URL 中最多包含 2,048 个字符。上述图像请求限制不仅适用于变量，也适用于有关浏览器、操作系统及浏览器插件（仅限 Netscape/Mozilla）的信息。

