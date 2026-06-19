---
title: 插件概述
description: 将代码粘贴到您的网站上以引入新功能。
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ImzoBRU0DajPc99vRlu1698CteFNk9dOS2OZrN9DBZs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 79%

---

# 插件概述

插件是可执行多个高级功能以帮助您实施 Analytics 的代码片段。 这些插件扩展了 JavaScript 文件的功能，提供了多项基本实施所没有的功能。 作为高级解决方案的一部分，Adobe 提供了许多其他插件。

{{plug-in}}

Adobe 提供了多种安装给定插件的方法：

* 通过Adobe Analytics扩展使用“常用Analytics插件”扩展
* 使用自定义代码编辑器粘贴插件代码
* 将插件代码粘贴到 `AppMeasurement.js` 文件

由于每个组织有不同的实施需求，因此您可以决定在实施中以何种方式包含这些插件。 将代码包含到网站中时，确保符合以下条件：

1. 首先，实例化 Analytics 跟踪对象（使用 [`s_gi`](../functions/s-gi.md)）。
   * 启用了标记的网站会在加载 Adobe Analytics 时自动实例化跟踪对象。
   * 使用 `AppMeasurement.js` 进行实施时，通常会初始化位于 JavaScript 文件顶部的跟踪对象。
2. 第二，包含插件代码。
   * “常用 Analytics 插件”扩展具有一个操作配置，您可以通过该配置初始化插件。
   * 如果您不想使用扩展，则可以在配置 Analytics 扩展时将插件代码粘贴到自定义代码编辑器中。
   * 如果您的实施不使用 Adobe Experience Platform 中的标记，则可以在实例化跟踪对象后将插件代码粘贴到 `AppMeasurement.js` 的任意位置。
3. 第三，调用插件。
   * 所有实施（包括启用了标记的网站的内部和外部实施）均使用 JavaScript 调用插件。 调用插件时将使用相应插件页面上记录的格式。
4. 验证您的实施并发布。

有许多组织使用 [`doPlugins`](../functions/doplugins.md) 函数来调用插件。 虽然此函数不是必需的，但 Adobe 认为使用此函数符合优秀实践。 AppMeasurement 会在调用此函数后立即编译和发送图像请求，这是一种理想做法，因为有多个插件依赖于其他 Analytics 变量。

## 弃用的插件

以下插件已停用。 如果您在旧版实施中遇到这些问题，请在此处记录这些问题以供参考。

* **`getPageLoadTime`**：使用JavaScript性能对象测量页面完全加载所花费的时间。 不再支持该代码，因为其代码依赖于[`PerformanceTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)接口，该接口在大多数现代浏览器中已弃用。 没有直接替换，并且不再提供安装说明和插件代码。
