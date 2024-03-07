---
description: 有关 Adobe Analytics 所收集数据和其他隐私注意事项的概述。
keywords: 隐私
title: 隐私概述
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 3%

---

# 隐私概述

Adobe希望您的组织能够遵守适用的法律和法规。 请参阅 [Adobe Experience Cloud隐私](https://www.adobe.com/cn/privacy/experience-cloud.html){target=_blank} 以了解更多信息。 在Adobe Analytics与您的组织之间，Adobe充当“数据处理者”，而您是“数据控制者”（或适用隐私和数据保护法律下相当）。 贵组织自行决定如何使用Adobe产品和服务，因为贵组织对于如何实施Adobe解决方案拥有完全控制权。 在使用Adobe Analytics时，贵组织有责任遵守您自己的隐私政策、您与Adobe的服务协议以及所有适用法律。

Adobe强烈建议遵循以下总体概念：

* **如果您收集个人数据，请确保遵守隐私法律法规。** 自定义变量允许您收集几乎任何您可以访问的内容；但是，您还必须考虑组织的隐私政策和适用法律。
* **向客户提供易于查找且易于理解的隐私信息，让您的组织了解这些信息。** 有用信息包括选择退出链接、如何使用其浏览数据以及您如何使用或计划使用Adobe的服务。
* **了解适用于您的本地法律和国际法律。** 如果贵组织在全球范围开展业务，则可能会适用某些国际法。

## 数据收集划分

Adobe提供了多个数据收集库来帮助将数据发送到Adobe。 重要示例包括：

* **AppMeasurement**：旨在将数据直接发送到Adobe Analytics的库。
* **Web SDK**：库旨在将数据发送到Adobe Experience Platform Edge Network，然后将该数据转发到Adobe Analytics。
* **标记**：基于Web的UI，允许您配置实施，而无需访问初始标记实施以外的网站或应用程序的源代码。 扩展可用于AppMeasurement和Web SDK。

Adobe Analytics可以收集以下类型的数据：

| 数据类型 | 详细信息 | 包含此数据的示例变量 |
| --- | --- | --- |
| 您网站上网页的页面名称或URL | Adobe Analytics需要此数据才能正常运行。 每次点击均需要URL或页面名称。 | [页面](../components/dimensions/page.md)， [页面URL](../components/dimensions/page-url.md) |
| 基于时间的数据 | Adobe Analytics需要此数据才能正常运行。 数据收集需要一个时间戳，并且基于时间的数据是从时间戳派生的。 | [页面逗留时间](../components/dimensions/time-spent-on-page.md)， [小时](../components/dimensions/hour-of-day.md)， [上午/下午](../components/dimensions/am-pm.md)， [工作日/周末](../components/dimensions/weekday-weekend.md)， [每周时间](../components/dimensions/day-of-week.md)， [月份](../components/dimensions/month-of-year.md) |
| 反向链接数据 | 默认情况下，数据收集库会在访客访问您的网站时收集反向链接URL。 您可以自定义实施以收集反向链接查询字符串中的数据。 这种做法适用于营销活动和跟踪广告效果。 | [反向链接](../components/dimensions/referrer.md)， [反向链接域](../components/dimensions/referring-domain.md) |
| 匿名访客ID | 数据收集库会为访问您网站的每个浏览器生成并引用访客ID。 此ID存储在Cookie中。 如果数据收集库无法设置Cookie标识符，则该库会使用匿名访客识别的回退方法。 此方法涉及使用访客的IP地址和用户代理字符串将相关点击绑定到同一访问。 如果您的组织启用了IP模糊处理，则此设置将被允许。 请参阅 [Adobe Analytics和浏览器Cookie](cookies/cookies.md) 以了解更多信息。 | [独特访客](../components/metrics/unique-visitors.md) |
| 可识别的访客ID | Adobe不会自动收集自定义访客ID。 但是，您可以自定义实施以收集此数据。 | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| 外部搜索词 | 外部搜索数据包括源自搜索引擎的关键字。 数据收集库会根据反向链接URL查找此数据。 但是，许多现代搜索引擎不再包含此信息。 | [搜索关键词](../components/dimensions/search-keyword.md) |
| 内部搜索词 | 内部搜索数据包括源自网站或应用程序搜索功能的关键字。 Adobe不会自动收集内部搜索数据。 但是，您可以自定义实施以收集此数据。 这种做法在使用Adobe Analytics的组织中很常见。 | [eVar](../components/dimensions/evar.md) |
| 计算机和浏览器规格 | 数据收集库会自动收集低熵浏览器提示，例如浏览器类型、操作系统类型以及设备是桌面还是移动设备。 需要自定义配置才能收集高熵提示，例如浏览器的特定版本/内部版本、设备型号或操作系统版本。 请参阅 [客户端提示概述](client-hints.md) 以了解更多信息。 | [浏览器](../components/dimensions/browser.md)， [操作系统](../components/dimensions/operating-systems.md)， [移动设备维度](../components/dimensions/mobile-dimensions.md)， [监视器分辨率](../components/dimensions/monitor-resolution.md) |
| 地理位置信息 | Adobe通过将IP地址的最后一个八位字节设置为0，提供了阻止详细地理位置的功能。 这样会降低地理信息的精确性，并且可以在以下位置设置： [报表包设置](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/general-acct-settings-admin.html). | [城市](../components/dimensions/cities.md)， [地区](../components/dimensions/regions.md)， [国家/地区](../components/dimensions/countries.md) |
| IP 地址 | Adobe提供在存储此数据时模糊处理（哈希）或完全删除访客IP地址的功能。 默认情况下，EMEA客户的IP地址设置通常会进行模糊处理。 无论使用何种模糊处理设置，IP地址都不可用作Analysis Workspace中的维度；它仅包含在 [数据馈送](../export/analytics-data-feed/data-feed-overview.md). 请参阅 [常规帐户设置](../admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) 有关可用混淆设置的详细信息，请参阅管理员指南。 | 无 |
| 您网站上提供的表单信息 | 所有实施类型都需要配置才能收集此数据。 您可以将此数据包含在自定义变量中。 | [eVar](../components/dimensions/evar.md) |
| 单击您网站上的广告或链接 | 收集条件 [`trackExternalLinks`](../implement/vars/config-vars/trackexternallinks.md) 或 [`trackDownloadLinks`](../implement/vars/config-vars/trackdownloadlinks.md) 已启用。 启用Activity Map时，会提供其他信息，例如点击的位置。 | [Activity Map](../analyze/activity-map/activity-map.md)， [退出链接](../components/dimensions/exit-link.md)， [下载链接](../components/dimensions/download-link.md) |
| 在您的网站上购买的产品 | 所有实施类型都需要配置才能收集此数据。 Adobe提供了多个默认变量来收集此信息。 | [产品](../components/dimensions/product.md)， [订购](../components/metrics/orders.md)， [收入](../components/metrics/revenue.md) |

{style="table-layout:auto"}

请参阅下的导航菜单 [Dimension概述](../components/dimensions/overview.md) 和 [量度概述](../components/metrics/overview.md) 以了解更多Adobe可能在下收集数据的变量。

## 数据处理位置

Adobe为Adobe Analytics维护三个数据处理位置。 这些站点接收原始数据并将其处理到报表包中，该报表包针对数据存储和报表检索进行了优化。 这些数据处理地点目前位于美国（俄勒冈）、英国（伦敦）和新加坡。 请参阅 [Adobe Analytics安全概述](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} 以了解更多信息。
