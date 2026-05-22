---
title: H 代码 JavaScript 实施概述
description: 了解在您的网站上实施 H 代码的工作流。
feature: Implementation Basics
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
role: Developer
TQID: 'https://experienceleague.adobe.com/-d3QyBm0RW5arsRHNHY4ov7YJxVFZrNdvXhVIuU6Ih4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 388
ht-degree: 73%

---

# H 代码 JavaScript 实施概述

>[!IMPORTANT]
>
>不再支持此版本的数据收集。 升级到 [Adobe Experience Platform 中的标记](../../launch/overview.md)或 [AppMeasurement for JavaScript](../overview.md)。

您必须能够访问托管服务器，才能成功为页面实施用于收集数据的代码。 以下步骤详细说明了如何进行基本的 Analytics H 代码实施。

>[!NOTE]
>
>在按以下说明操作之前，您必须已拥有 `s_code.js` 的副本。 Adobe 将不再提供用于在代码管理器中下载 H 代码的选项。

1. **更新核心 JS 文件变量**：编辑 `s_code.js` 文件，并确保已更新以下变量：
   * `s_account` 包含要将数据发送到的报表包 ID。 请参阅
   * `s.trackingServer` 包含 Cookie 的存储位置。 请参阅 [trackingServer](../../vars/config-vars/trackingserver.md)。
1. **将 `s_code.js` 文件托管在您的网站上**：此文件通常与其他脚本一起驻留在您的 Web 服务器中。
1. **在所有页面上引用 `s_code.js`**：确保所有页面都调用核心 JavaScript 文件，并在 HTML `<body>` 标记（而非 `<head>` 标记）中调用该文件。

   >[!TIP]
   >
   >H 代码要求在 `s_code.js` 标记中调用 `<body>` 脚本。 这与其他实施方法有所不同，因为大多数实施方法要求在 `<head>` 标记中引用脚本。
1. **在每个页面上定义特定于页面的变量**：应在每个页面上定义各个变量，如页面名称或 eVar。 在每个页面上通常使用内联 `<script>` 标记来定义各个变量。
1. **使用调试器验证数据收集**：下载并安装[CX Enterprise Debugger](../../validate/debugger.md)，以确保将数据发送到Adobe，且已正确定义页面变量。

## 缓存

JavaScript文件在最初加载后，会缓存在访客的浏览器中，并且通常不会为每个会话下载多次。 不会在每个页面上下载文件，即使网站上的每个页面都使用了该文件。 在大多数网站上，用户在每个会话内平均都会查看多个页面，因此将使用多次的JavaScript转移到此文件中可减少总体下载数据量。

## H 代码压缩

如果您担心下载的 `s_code.js` 文件过大，Adobe 建议使用 GZIP 压缩 `s_code.js` 文件。 所有主要浏览器都支持 GZIP，与 JavaScript 压缩相比，其压缩的效果更好。 请参阅 Apache 文档中的 [Apache 模块 mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html)。
