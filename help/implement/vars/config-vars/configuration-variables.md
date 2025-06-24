---
title: 配置变量
description: 使用配置变量可帮助确定数据收集的方式。
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 65%

---

# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。此类变量通常不包含维度或量度值。

## 设置配置变量

在使用Web SDK扩展或Analytics扩展的实施中，通常可以在扩展的设置中找到配置变量：

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 单击“扩展”选项卡，然后单击扩展下的“配置”。

在使用 `AppMeasurement.js` 的 JavaScript 实施中，通常会在 JS 文件的顶部设置配置变量。

>[!IMPORTANT]
>
>确保在调用跟踪方法（[`t()`](../functions/t-method.md)或[`tl()`](../functions/tl-method.md)）之前设置所有配置变量。 避免在 [`doPlugins()`](../functions/doplugins.md) 函数中设置配置变量。
