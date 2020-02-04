---
title: 有关 Analytics 实施的常见问题解答
description: 有关实施的常见问题，以及指向更多信息的链接。
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# 有关 Analytics 实施的常见问题解答

有关实施的常见问题，以及指向更多信息的链接。

**变量分配和过期之间有何差异？**

分配和过期都是可应用于自定义变量的设置。 *当您具有* 持续存在的变量值和新的变量值时，分配即开始发挥作用。 它决定是保留旧值还是保留新值。 *当您不希望* 变量值继续保持时，Expiration即开始生效。

**Experience cloud访客ID与Analytics访客ID之间有何差异？**

标识服务会分配一个唯一的永久标识符，该标识符可以在Experience cloud中的其他解决方案之间共享。 Analytics访客ID仅供Analytics使用。 Adobe建议在您的实施中使用Experience Cloud访客ID服务。

**如果阻止cookie，如何设置访客ID?**

If the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2-year expiration and is used as the fallback identification method going forward.

**如何实现心跳视频跟踪？**

请参阅[在 Adobe Analytics 中测量音频和视频](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html)。

**Adobe的服务中断是否会影响性能？**

不会。JavaScript文件不托管在Adobe服务器上，因此Adobe中断不会影响您的AppMeasurement库。 如果您使用Adobe Experience Platform Launch，则JavaScript文件由Akamai托管，或位于由您的组织确定的服务器位置。

**从浏览器向Adobe服务发送数据是否会降低性能？**

AppMeasurement在HTML页面中创建一个图像对象，然后浏览器从Adobe数据收集服务器请求该图像对象。 如果数据收集服务器速度缓慢或无响应，则该请求的线程处理将延迟到图像返回或超时发生。 因为浏览器会通过多线程处理图像，而 Adobe 故障仅占用一个线程，其他线程继续工作，因此对页面加载时间会造成一定的影响，但这个影响极小。

**如何跟踪移动应用程序？**

您可以使用Adobe Experience Platform SDK。 有关更 [多信息，请参阅Adobe Experience Platform SDK概述](https://aep-sdks.gitbook.io/docs/) 。

**什么是插件？**

插件是执行高级功能的代码片段。 它们扩展了AppMeasurement的功能，为您的实施提供更多功能。
