---
title: 配置变量
description: 使用配置变量帮助确定如何收集数据。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。它们通常不包含维或度量值。

## 设置配置变量

在使用的JavaScript实 `AppMeasurement.js`施中，配置变量通常设置在JS文件的顶部。

在使用Adobe Experience Platform Launch的实施中，配置变量通常可通过配置Adobe Analytics扩展找到：

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)/cn。
2. 单击要编辑的属性。
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] 在调用跟踪方法（或）之前，请确保已设置所[`t()`](../functions/t-method.md) 有配置 [`tl()`](../functions/tl-method.md)变量。 避免在函数中设置配置 [`doPlugins()`](../functions/doplugins.md) 变量。
