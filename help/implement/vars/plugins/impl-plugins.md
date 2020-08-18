---
title: 插件概述
description: 将代码粘贴到您的网站上以引入新功能。
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 83%

---


# 插件概述

插件是可执行多个高级功能以帮助您实施 Analytics 的代码片段。这些插件扩展了 JavaScript 文件的功能，提供了多项基本实施所没有的功能。作为高级解决方案的一部分，Adobe 提供了许多其他插件。

>[!IMPORTANT]
>
>这些插件均由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对其中任何插件的支持，包括安装或疑难解答。如果您需要关于某个插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

Adobe 提供了多种安装给定插件的方法：

1. 通过 Adobe Experience Platform Launch 使用“常用 Analytics 插件”扩展
2. 使用 Launch 自定义代码编辑器粘贴插件代码
3. 将插件代码粘贴到 `AppMeasurement.js` 文件

由于每个组织有不同的实施需求，因此您可以决定在实施中以何种方式包含这些插件。将代码包含到网站中时，确保符合以下条件：

1. 首先，实例化 Analytics 跟踪对象（使用 [`s_gi`](../functions/s-gi.md)）。
   * Launch 会在加载 Adobe Analytics 时自动实例化跟踪对象。
   * 使用 `AppMeasurement.js` 进行实施时，通常会初始化位于 JavaScript 文件顶部的跟踪对象。
2. 第二，包含插件代码。
   * “常用 Analytics 插件”扩展具有一个操作配置，您可以通过该配置初始化插件。
   * 如果您不想使用扩展，可以在配置Analytics扩展时在自定义代码编辑器中粘贴插件代码。
   * 如果您的实施不使用 Launch，则可以在实例化跟踪对象后将插件代码粘贴到 `AppMeasurement.js` 的任意位置。
3. 第三，调用插件。
   * 所有实施（包括 Launch 内部和外部的实施）均使用 JavaScript 调用插件。调用插件时将使用相应插件页面上记录的格式。
4. 验证您的实施并发布。

有许多组织使用 [`doPlugins`](../functions/doplugins.md) 函数来调用插件。虽然此函数不是必需的，但 Adobe 认为使用此函数符合最佳实践。AppMeasurement 会在调用此函数后立即编译和发送图像请求，这是一种理想做法，因为有多个插件依赖于其他 Analytics 变量。

## 将插件与非标准跟踪对象一起使用

默认情况下，插件不能用于跟踪对象（非跟踪对象） `s`。 但是，您可以修改插件代码以适应自定义跟踪对象。 在给定的插件中，将对的所有引用替换 `s` 为所需的跟踪对象。
