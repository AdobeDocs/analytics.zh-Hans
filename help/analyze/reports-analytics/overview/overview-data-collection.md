---
description: 了解如何为 Adobe Analytics 收集数据。
solution: Analytics
subtopic: Get started
title: 关于数据收集
topic: Reports and analytics
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 关于数据收集

了解如何为 Adobe Analytics 收集数据。

Adobe 跟踪的每个页面均有一个 Adobe 授权的 JavaScript 代码小片段。您的帐户管理员可提供该代码。

高级别下的数据收集过程如下：

![](assets/data_collection.png)

1. 访客访问包含数据收集代码的网页。
1. 页面加载时，数据收集代码会向 Adobe 数据收集服务器发送图像请求（也称为网站信标）。图像请求包含您要收集的有关访客与您的网站交互的数据。
1. Adobe 在报表包中存储这些数据。您可以登录以访问报表包数据，并生成与访客在您网站上的活动相关的报表。

数据收集速度很快，不会明显影响页面加载时间。收集的数据包括通过单击浏览器&#x200B;**重新加载**&#x200B;或&#x200B;**后退**&#x200B;按钮获得的页面查看次数。从缓存中检索页面时，JavaScript 代码仍将运行。

请参 [阅Analytics中的数据收集。](/help/import/home.md)
