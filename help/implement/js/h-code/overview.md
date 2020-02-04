---
title: H代码JavaScript实现概述
description: 了解在您的站点上实施H代码的工作流程。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# H代码JavaScript实现概述

> [!IMPORTANT] 不再支持此版本的数据收集。 升级到 [Adobe Experience Platform Launch](../../launch/overview.md) 或 [AppMeasurement for javaScript](../overview.md)。

您必须具有访问托管服务器的权限才能成功实施包含代码的页面以收集数据。 以下步骤将指导您完成基本的Analytics h代码实施。

> [!NOTE] 您必须已拥有一个现有的副本， `s_code.js` 才能按照这些说明操作。 Adobe不再提供在代码管理器中下载H代码的选项。

1. **更新核心JS文件变量**:编辑文 `s_code.js` 件并确保更新了以下变量：
   * `s_account` 包含要将数据发送到的报表包ID。 请参阅
   * `s.trackingServer` 包含存储的位置cookie。 请参阅 [trackingServer](../../vars/config-vars/trackingserver.md)。
2. **在您的`s_code.js`站点上托管文件**:此文件通常驻留在Web服务器上的其他脚本中。
3. **所有`s_code.js`页面上的引用**:确保所有页面都调用核心JavaScript文件，并在HTML标记(而非标 `<body>` 记)中执行 `<head>` 该操作。
   > [!TIP] H代码要求在标 `s_code.js` 记中调用该脚 `<body>` 本。 这与其他实现方法不同，大多数实现方法需要脚本引用位于标 `<head>` 记中。
4. **在每个页面上定义特定于页面的变量**:每个页面都应定义各个变量，如页面名称或eVar。 每个页面上通常使用内联标 `<script>` 记来定义各个变量。
5. **使用调试器验证数据收集**:下载并安装 [Experience cloud调试器](../../validate/debugger.md) ，以确保数据已发送到Adobe，且页面变量已正确定义。

## 缓存

JavaScript 文件首次加载后会缓存在访客的浏览器中，通常情况下，针对每个会话至多下载一次。即使网站上的每个页面都使用该文件，也不会为每个页面下载它。在大多数网站上，用户在每个会话内平均都会查看多个页面，因此将使用多次的 JavaScript 转移到此文件中可减少总体下载数据量。

## H代码压缩

如果您担心文件的下载大小， `s_code.js` Adobe建议使用GZIP压 `s_code.js` 缩文件。 GZIP受所有主要浏览器支持，与JavaScript压缩相比，它具有更好的性能。 请参 [阅Apache文档中的Apache Module mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) 。
