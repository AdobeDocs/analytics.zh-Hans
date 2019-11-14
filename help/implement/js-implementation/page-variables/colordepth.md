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


# colorDepth

 变量用于显示屏幕上各像素颜色的位数。

<!-- 

colordepth.xml

 -->

例如，32 表示屏幕上显示的是 32 位色。此变量填充在页面代码之后，运行 *`doPlugins`* 之前。

> [!NOTE]此变量只可读取，不得设置。

您可以读取这些值，并将它们复制到 `props/eVars`，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| c | 8、16 和 32 | 32 | “流量”&gt;“技术”&gt;“显示器颜色深度” |
