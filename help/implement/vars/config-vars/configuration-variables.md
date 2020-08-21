---
title: 配置变量
description: 使用配置变量可帮助确定数据收集的方式。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '123'
ht-degree: 100%

---


# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。此类变量通常不包含维度或量度值。

## 设置配置变量

在使用 `AppMeasurement.js` 的 JavaScript 实施中，通常会在 JS 文件的顶部设置配置变量。

在使用 Adobe Experience Platform Launch 的实施中，通常通过配置 Adobe Analytics 扩展来查找配置变量：

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击要编辑的属性。
3. 单击[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]。

>[!IMPORTANT]
>
>确保在调用跟踪方法（[`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)）之前设置所有配置变量。避免在 [`doPlugins()`](../functions/doplugins.md) 函数中设置配置变量。
