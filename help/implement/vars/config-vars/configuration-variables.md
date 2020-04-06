---
title: 配置变量
description: 使用配置变量可帮助确定数据收集的方式。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。此类变量通常不包含维度或量度值。

## 设置配置变量

在使用 `AppMeasurement.js` 的 JavaScript 实施中，通常会在 JS 文件的顶部设置配置变量。

在使用 Adobe Experience Platform Launch 的实施中，通常通过配置 Adobe Analytics 扩展来查找配置变量：

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)/cn。
2. 单击要编辑的属性。
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

>[!IMPORTANT] 在调用跟踪方法（或）之前，请确保已设置所[`t()`](../functions/t-method.md) 有配置 [`tl()`](../functions/tl-method.md)变量。 避免在 [`doPlugins()`](../functions/doplugins.md) 函数中设置配置变量。
