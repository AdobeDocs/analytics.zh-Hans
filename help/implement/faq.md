---
title: 有关 Analytics 实施的常见问题解答
description: 有关实施的常见问题，以及指向更多信息的链接。
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# 有关 Analytics 实施的常见问题解答

有关实施的常见问题，以及指向更多信息的链接。

**变量分配和过期之间有何区别？**

分配和过期都是可应用于自定义变量的设置。当您同时具有持久变量值和新变量值时，则需要使用&#x200B;*分配*&#x200B;设置。该设置可决定是保留旧值或新值。当您不希望持续保留某个变量值时，则需要使用&#x200B;*过期*&#x200B;设置。

**Experience Cloud 访客 ID 与 Analytics 访客 ID 之间有何区别？**

Identity Service 可分配一个唯一的永久标识符，该标识符可以在 Experience Cloud 中的其他解决方案之间共享。而 Analytics 访客 ID 仅供 Analytics 使用。Adobe 建议在您的实施中使用 Experience Cloud 访客 ID 服务。

**如果阻止 Cookie，该如何设置访客 ID？**

只要遇到标准 `s_vi` Cookie 不可用的情况，就会在网站的域中通过一个随机生成的唯一 ID 创建一个回退 Cookie。这个 Cookie 名为 `s_fid`，具有 2 年期限，可用作今后的回退识别方法。

**我该如何实施心率视频跟踪？**

请参阅[在 Adobe Analytics 中测量音频和视频](https://docs.adobe.com/content/help/zh-Hans/media-analytics/using/media-overview.html)。

**Adobe 的服务中断会影响库性能吗？**

不会。由于 JavaScript 文件并非是在 Adobe 服务器上托管，因此 Adobe 的故障将不会影响 AppMeasurement 库。如果您使用 Adobe Experience Platform Launch，则 JavaScript 文件由 Akamai 托管，或者托管在由贵组织确定的服务器位置上。

**将来自浏览器的数据发送至 Adobe 服务会降低性能吗？**

AppMeasurement 会在 HTML 页面内创建一个图像对象，浏览器随后从 Adobe 数据收集服务器请求该图像对象。如果数据收集服务器变得缓慢或无反应，则处理该请求的线程将被延迟，直至图像返回或发生超时。因为浏览器会通过多线程处理图像，而 Adobe 故障仅占用一个线程，其他线程继续工作，因此对页面加载时间会造成一定的影响，但这个影响极小。

**我该如何跟踪移动设备应用程序？**

您可以使用 Adobe Experience Platform SDK。有关更信息，请参阅 [Adobe Experience Platform SDK 概述](https://aep-sdks.gitbook.io/docs/)。

**什么是插件？**

插件是可执行高级功能的代码片段。插件可扩展 AppMeasurement 的功能，以便您在实施中可以提供更多功能。
