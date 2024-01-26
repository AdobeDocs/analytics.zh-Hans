---
title: 插件概述
description: 将代码粘贴到您的网站上以引入新功能。
feature: Variables
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 96%

---

# 插件概述

插件是可执行多个高级功能以帮助您实施 Analytics 的代码片段。这些插件扩展了 JavaScript 文件的功能，提供了多项基本实施所没有的功能。作为高级解决方案的一部分，Adobe 提供了许多其他插件。

{{plug-in}}

Adobe 提供了多种安装给定插件的方法：

* 通过Adobe Analytics扩展使用“常用Analytics插件”扩展
* 使用自定义代码编辑器粘贴插件代码
* 将插件代码粘贴到 `AppMeasurement.js` 文件

由于每个组织有不同的实施需求，因此您可以决定在实施中以何种方式包含这些插件。将代码包含到网站中时，确保符合以下条件：

1. 首先，实例化 Analytics 跟踪对象（使用 [`s_gi`](../functions/s-gi.md)）。
   * 启用了标记的网站会在加载 Adobe Analytics 时自动实例化跟踪对象。
   * 使用 `AppMeasurement.js` 进行实施时，通常会初始化位于 JavaScript 文件顶部的跟踪对象。
2. 第二，包含插件代码。
   * “常用 Analytics 插件”扩展具有一个操作配置，您可以通过该配置初始化插件。
   * 如果您不想使用扩展，则可以在配置 Analytics 扩展时将插件代码粘贴到自定义代码编辑器中。
   * 如果您的实施不使用 Adobe Experience Platform 中的标记，则可以在实例化跟踪对象后将插件代码粘贴到 `AppMeasurement.js` 的任意位置。
3. 第三，调用插件。
   * 所有实施（包括启用了标记的网站的内部和外部实施）均使用 JavaScript 调用插件。调用插件时将使用相应插件页面上记录的格式。
4. 验证您的实施并发布。

有许多组织使用 [`doPlugins`](../functions/doplugins.md) 函数来调用插件。虽然此函数不是必需的，但 Adobe 认为使用此函数符合优秀实践。AppMeasurement 会在调用此函数后立即编译和发送图像请求，这是一种理想做法，因为有多个插件依赖于其他 Analytics 变量。
