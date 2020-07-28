---
title: H 代码 JavaScript 实施概述
description: 了解在您的网站上实施 H 代码的工作流。
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 100%

---


# H 代码 JavaScript 实施概述

>[!IMPORTANT]
>
> 不再支持此版本的数据收集。升级到 [Adobe Experience Platform Launch](../../launch/overview.md) 或 [AppMeasurement for JavaScript](../overview.md)。

您必须能够访问托管服务器，才能成功为页面实施用于收集数据的代码。以下步骤详细说明了如何进行基本的 Analytics H 代码实施。

>[!NOTE]
>
> 在按以下说明操作之前，您必须已拥有 `s_code.js` 的副本。Adobe 将不再提供用于在代码管理器中下载 H 代码的选项。

1. **更新核心 JS 文件变量**：编辑 `s_code.js` 文件，并确保已更新以下变量：
   * `s_account` 包含要将数据发送到的报表包 ID。请参阅
   * `s.trackingServer` 包含 Cookie 的存储位置。请参阅 [trackingServer](../../vars/config-vars/trackingserver.md)。
2. **将`s_code.js`文件托管在您的网站上**：此文件通常与其他脚本一起驻留在您的 Web 服务器中。
3. **在所有页面上引用`s_code.js`**：确保所有页面都调用核心 JavaScript 文件，并在 HTML `<body>` 标记（而非 `<head>` 标记）中调用该文件。

   >[!TIP] H 代码要求在 `<body>` 标记中调用 `s_code.js` 脚本。这与其他实施方法有所不同，因为大多数实施方法要求在 `<head>` 标记中引用脚本。
4. **在每个页面上定义特定于页面的变量**：应在每个页面上定义各个变量，如页面名称或 eVar。在每个页面上通常使用内联 `<script>` 标记来定义各个变量。
5. **使用调试器验证数据收集**：下载并安装 [Experience Cloud 调试器](../../validate/debugger.md)，以确保将数据发送到 Adobe，且已正确定义页面变量。

## 缓存

JavaScript 文件首次加载后会缓存在访客的浏览器中，通常情况下，针对每个会话至多下载一次。即使网站上的每个页面都使用该文件，也不会为每个页面下载它。在大多数网站上，用户在每个会话内平均都会查看多个页面，因此将使用多次的 JavaScript 转移到此文件中可减少总体下载数据量。

## H 代码压缩

如果您担心下载的 `s_code.js` 文件过大，Adobe 建议使用 GZIP 压缩 `s_code.js` 文件。所有主要浏览器都支持 GZIP，与 JavaScript 压缩相比，其压缩的效果更好。请参阅 Apache 文档中的 [Apache 模块 mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html)。
