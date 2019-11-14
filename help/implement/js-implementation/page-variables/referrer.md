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


# referrer

 变量可用于还原丢失的反向链接信息。

<!-- 

referrer.xml

 -->

通常情况下，我们通过服务器端和 JavaScript 重定向将访客转至适当的位置。但是，重定向浏览器时，原始反向链接 URL 将丢失。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 255 字节 | R | “流量”&gt;“查找方法转化”&gt;“查找方法” | document.referrer |

许多公司在其整个网站中的许多地方使用重定向。例如，可以从某个搜索引擎付费搜索结果将访客重定向。重定向浏览器时，反向链接通常会丢失。The *`referrer`* 变量可用于在重定向后还原首页上的原始 *`referrer`* 值。*`referrer`* 可通过服务器端填充，或通过查询字符串 JavaScript 填充。

若要 Analytics 记录反向链接，其格式必须正确，即必须遵循标准 URL 格式，并且包含协议和相应的位置。

**语法和可能值** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

只能在 *`referrer`*. 请确保字符串为 URL 编码（无空格）。

**示例** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**配置设置** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

无

**缺陷、问题和提示** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

*`referrer`* 必须是标准 URL，并且包括协议。
