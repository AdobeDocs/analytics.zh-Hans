---
title: 配置变量
description: 使用配置变量可帮助确定数据收集的方式。
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '125'
ht-degree: 100%

---

# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。此类变量通常不包含维度或量度值。

## 设置配置变量

在使用 `AppMeasurement.js` 的 JavaScript 实施中，通常会在 JS 文件的顶部设置配置变量。

在使用 Adobe Experience Platform 标记的实施中，通常通过配置 Adobe Analytics 扩展来查找配置变量：

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
1. 单击要编辑的属性。
1. 单击[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]。

>[!IMPORTANT]
>
>确保在调用跟踪方法（[`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)）之前设置所有配置变量。避免在 [`doPlugins()`](../functions/doplugins.md) 函数中设置配置变量。
