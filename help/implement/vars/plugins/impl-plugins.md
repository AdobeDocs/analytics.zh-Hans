---
title: 插件概述
description: 将代码粘贴到您的站点上以引入新功能。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# 插件概述

插件是执行多个高级功能以帮助您实施Analytics的代码片段。 这些插件扩展了 JavaScript 文件的功能，提供了多项基本实施所没有的功能。作为高级解决方案的一部分，Adobe 提供了许多其他插件。

> [!IMPORTANT] Adobe Consulting出于好意提供插件，以帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不为这些插件提供支持，包括安装或疑难解答。 如果您需要插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

Adobe提供多种安装给定插件的方法：

1. 使用Adobe Experience Platform Launch使用“常用分析插件”扩展
2. 使用启动自定义代码编辑器粘贴插件代码
3. 将插件代码粘贴到文 `AppMeasurement.js` 件

每个组织有不同的实施需求，因此您可以决定如何将它们纳入实施。 确保在站点中包含代码时符合以下条件：

1. 首先实例化Analytics跟踪对象(使 `s_gi`用)。
   * Launch在加载Adobe Analytics时自动实例化跟踪对象。
   * 使用的实 `AppMeasurement.js` 现通常初始化JavaScript文件顶部的跟踪对象。
2. 请随时包含插件代码。
   * “常用分析插件”扩展具有一个操作配置，您可以在该配置中初始化插件。
   * 如果您不想使用插件，可以在配置Analytics扩展时在自定义代码编辑器中粘贴插件代码。
   * 如果您的实现不使用Launch，则可以在实例化跟踪对象后将插件代 `AppMeasurement.js` 码粘贴到任意位置。
3. 呼叫增效工具第三部分。
   * 所有实现（在Launch内部和外部）都使用JavaScript调用插件。 使用插件页面上记录的格式调用插件。
4. 验证您的实施并发布。

许多组织使用该功能调用插 [`doPlugins`](../functions/doplugins.md) 件。 虽然此功能不是必需的，但Adobe认为使用此功能是最佳实践。 AppMeasurement在编译和发送图像请求之前调用此函数，这非常理想，因为多个插件依赖于其他Analytics变量。
