---
title: 配置变量
description: 使用配置变量可帮助确定数据收集的方式。
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 64%

---

# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。此类变量通常不包含维度或量度值。

## 设置配置变量

在使用 `AppMeasurement.js` 的 JavaScript 实施中，通常会在 JS 文件的顶部设置配置变量。

在使用Adobe Experience Platform标记的实施中，通常通过配置Adobe Analytics扩展来找到配置变量：

1. 转到`experience.adobe.com`并在出现提示时登录。
1. 选择[!UICONTROL 启动/数据收集]。
1. 单击[!UICONTROL 转到Launch /数据收集]，然后选择[!UICONTROL 标记]。
1. 单击要编辑的属性。
1. 单击[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]。

>[!IMPORTANT]
>
>确保在调用跟踪方法（[`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)）之前设置所有配置变量。避免在 [`doPlugins()`](../functions/doplugins.md) 函数中设置配置变量。
