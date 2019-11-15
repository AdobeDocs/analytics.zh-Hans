---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# javascriptVersion

 变量表示受浏览器支持的 JavaScript 的版本。

<!-- 

javascriptVersion.xml

 -->

此变量填充在页面代码之后，运行 *`doPlugins`* 之前。

> [!NOTE]此变量只可读取，不得设置。

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | “流量”&gt;“技术”&gt;“JavaScript 版本” |

H.10 和更高版本的 JavaScript 文件可以准确检测到最高 1.7 版本（这是 H.10 发布时的最高版本）。以前版本的 JavaScript 文件最高只能检测到 1.3 版本
