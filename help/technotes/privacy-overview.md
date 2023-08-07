---
description: 有关 Adobe Analytics 所收集数据和其他隐私注意事项的概述。
keywords: 隐私
title: 隐私概述
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: ee0bf5beeac3c9780eb0c8420845114f7e840aec
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 12%

---

# 隐私概述

访客可以进一步了解 Adobe 通常如何使用在 [Adobe 隐私中心](https://www.adobe.com/cn/privacy.html)收集的信息。这取决于贵组织是否披露 Adobe 产品和服务的用途，因为贵组织对于如何实施 Adobe 服务具有完全控制权。贵组织有责任遵守您自己的隐私政策、您与Adobe的服务协议以及所有适用法律。

Adobe强烈建议遵循以下总体概念：

* **避免在Adobe Analytics中收集个人身份信息。** 自定义变量允许您收集几乎任何您可以访问的内容；但是，您还必须考虑组织的隐私政策和适用法律。
* **向访客提供关于选择退出信息的易于查找和理解的信息。** 允许他们选择退出任何非绝对必要的活动。 欧盟中的大多数国家/地区并不认为 Analytics Cookie 绝对必要。

## 数据收集划分

Adobe Analytics会自动收集或可能收集以下类型的数据：

| 数据类型 | 详细信息 | 包含此数据的示例变量 |
| --- | --- | --- |
| 您网站上网页的页面名称或URL | 总是收集的。 每次点击均需要URL或页面名称。 | [页面](../components/dimensions/page.md)， [页面URL](../components/dimensions/page-url.md) |
| 基于时间的数据 | 总是收集的。 数据收集需要时间戳，并且基于时间的数据是从时间戳派生的。 | [页面逗留时间](../components/dimensions/time-spent-on-page.md)， [小时](../components/dimensions/hour-of-day.md)， [上午/下午](../components/dimensions/am-pm.md)， [工作日/周末](../components/dimensions/weekday-weekend.md)， [每周时间](../components/dimensions/day-of-week.md)， [月份](../components/dimensions/month-of-year.md) |
| 来自其他网站网页的数据 | Adobe无法收集非关联网站上的数据，而您无法更改网站的源代码。 当访客访问您的网站时，AppMeasurement会自动收集反向链接URL。 您可以自定义实施，以便在查询字符串到达您的网站后收集其中的数据。 | [反向链接](../components/dimensions/referrer.md)， [反向链接域](../components/dimensions/referring-domain.md) |
| 匿名访客ID | AppMeasurement会自动为访问您网站的每个浏览器生成并引用访客ID。 此ID存储在Cookie中。 如果给定实施没有Cookie可用，Adobe Analytics会使用回退方法，通过IP地址和用户代理字符串进行访客识别。 请参阅 [Adobe Analytics和浏览器Cookie](cookies/cookies.md) 以了解更多信息。 | [独特访客](../components/metrics/unique-visitors.md) |
| 可识别的访客ID | Adobe不会自动收集自定义访客ID。但是，您可以自定义实施以收集此数据。 | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| 外部搜索词 | AppMeasurement会尝试根据反向链接URL自动收集此数据。 但是，许多现代搜索引擎不再包含此信息。 | [搜索关键词](../components/dimensions/search-keyword.md) |
| 内部搜索词 | Adobe不会自动收集内部搜索数据。 但是，您可以自定义实施以收集此数据，这是使用Adobe Analytics的组织常见的做法。 | [eVar](../components/dimensions/evar.md) |
| 计算机和浏览器规格 | AppMeasurement会自动收集低熵浏览器提示，例如浏览器类型、操作系统类型以及设备是桌面还是移动设备。 收集高熵提示需要进行配置，例如浏览器的特定版本/内部版本、设备型号或操作系统版本。 请参阅 [客户端提示概述](client-hints.md) 以了解更多信息。 | [浏览器](../components/dimensions/browser.md)， [操作系统](../components/dimensions/operating-systems.md)， [移动设备维度](../components/dimensions/mobile-dimensions.md)， [监视器分辨率](../components/dimensions/monitor-resolution.md) |
| 地理位置信息 | Adobe让您可以启用或禁用每个网站或应用程序（在报表包级别）的地理位置数据收集。 许多实施类型(包括AppMeasurement)都会自动收集此数据。 | [城市](../components/dimensions/cities.md)， [地区](../components/dimensions/regions.md)， [国家/地区](../components/dimensions/countries.md) |
| IP 地址 | Adobe提供在存储此数据时遮蔽最后一个八位字节或完全遮蔽访客IP地址的功能。 默认情况下，EMEA客户的IP地址通常完全遮蔽。 IP地址不能作为Adobe Analytics中的维度使用；它只包含在原始数据([数据馈送](../export/analytics-data-feed/data-feed-overview.md))。 | 无 |
| 您网站上提供的表单信息 | 所有实施类型都需要配置才能收集此数据。 您可以将此数据包含在自定义变量中。 | [eVar](../components/dimensions/evar.md) |
| 在您的网站上点击的广告或链接 | 使用AppMeasurement时自动收集。 启用Activity Map后，会提供其他信息，例如点击位置。 | [Activity Map](../analyze/activity-map/activity-map.md)， [退出链接](../components/dimensions/exit-link.md)， [下载链接](../components/dimensions/download-link.md) |
| 在您的网站上购买的产品 | 所有实施类型都需要配置才能收集此数据。 Adobe提供了多个默认变量来存储此信息。 | [产品](../components/dimensions/product.md)， [订购](../components/metrics/orders.md)， [收入](../components/metrics/revenue.md) |

{style="table-layout:auto"}

请参阅下的导航菜单 [Dimension概述](../components/dimensions/overview.md) 和 [量度概述](../components/metrics/overview.md) 以了解更多Adobe可能在下收集数据的变量。
