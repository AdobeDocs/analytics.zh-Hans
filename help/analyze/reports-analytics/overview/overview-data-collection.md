---
description: 了解如何为 Adobe Analytics 收集数据。
subtopic: Get started
title: 关于数据收集
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 34a7be55-519a-4e04-95a3-99b0f6e04b3e
source-git-commit: 4556ba78cb5cc449e2f43fef7067d7e776e61c6b
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 98%

---

# 关于数据收集

了解如何为 Adobe Analytics 收集数据。

高级别下的数据收集过程如下：

![](assets/data_collection.png)

1. 访客访问包含数据收集代码的网页。
1. 页面加载时，数据收集代码会向 Adobe 数据收集服务器发送图像请求（也称为网站信标）。图像请求包含您要收集的有关访客与您的网站交互的数据。
1. Adobe 在报表包中存储这些数据。您可以登录以访问报表包数据，并生成与访客在您网站上的活动相关的报表。

数据收集速度很快，不会明显影响页面加载时间。收集的数据包括通过单击浏览器&#x200B;**重新加载**&#x200B;或&#x200B;**后退**&#x200B;按钮获得的页面查看次数。从缓存中检索页面时，JavaScript 代码仍将运行。

请参阅 [Analytics 中的数据收集](/help/import/home.md)。
