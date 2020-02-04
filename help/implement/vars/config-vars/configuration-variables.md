---
title: 配置变量
description: 使用配置变量帮助确定如何收集数据。
translation-type: tm+mt
source-git-commit: e9a876a1f562333056387d63de46a9cfe3fb3939

---


# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。它们通常不包含维或度量值。

## 设置配置变量

在使用的JavaScript实 `AppMeasurement.js`施中，配置变量通常设置在JS文件的顶部。

在使用Adobe Experience Platform Launch的实施中，配置变量通常可通过配置Adobe Analytics扩展找到：

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)/cn。
2. 单击要编辑的属性。
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] 确保在调用跟踪函数（或）之前设置所`t()` 有配置 `tl()`变量。 避免在函数中设置配置 `doPlugins()` 变量。
