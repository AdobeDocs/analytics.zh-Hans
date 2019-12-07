---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---




# cookiesEnabled

 变量表示 JavaScript 是否可设置第一方会话 Cookie。


<!-- 

cookiesenabled.xml

 -->

此变量填充在页面代码之后，运行 *`doPlugins`* 之前。

> [!NOTE]此变量只可读取，不得设置。

您可以读取这些值，并将它们复制到 `props/eVars`，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 |
|---|---|---|
| k | Y 或 N | Y |
