---
description: 有关 Adobe Analytics 所收集数据和其他隐私注意事项的概述。
keywords: 隐私
title: 隐私概述
feature: Data Governance
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 98%

---

# 隐私概述

Adobe 希望帮助您的组织遵守适用的法律法规。有关详细信息，请参阅[Adobe Experience Cloud隐私](https://www.adobe.com/cn/privacy/experience-cloud.html){target=_blank}。 在 Adobe Analytics 和您的组织之间，Adobe 充当“数据处理者”，而您是“数据控制者”（或适用隐私和数据保护法下的同等角色）。这取决于贵组织是否披露 Adobe 产品和服务的用途，因为贵组织对于如何实施 Adobe 解决方案具有完全控制权。在使用 Adobe Analytics 时，组织有责任遵守自己的隐私政策、您与 Adobe 签订的服务协议以及所有适用法律。

Adobe 强烈建议遵守以下总体概念：

* **如果您收集个人数据，请确保遵守隐私法律和法规。** 自定义变量允许您收集几乎任何您可以访问的内容；但是，您还必须考虑组织的隐私政策和适用法律。
* **为您的组织向客户提供易于查找和理解的隐私信息。** 有用的信息，包括选择退出链接、如何使用其浏览数据，以及您如何使用或计划使用 Adobe 的服务。
* **了解适用于您的当地法律和国际法律。** 如果您的组织在全球范围内运作，则某些国际法律适用。

## 数据收集细分

Adobe 提供多个数据收集库来协助将数据发送到 Adobe。值得注意的例子包括：

* **AppMeasurement**：旨在将数据直接发送到 Adobe Analytics 的库。
* **Web SDK**：旨在将数据发送到 Adobe Experience Platform Edge 网络的库，然后由该网络将数据转发到 Adobe Analytics。
* **标记**：基于 Web 的用户界面，使您能够配置实施，而无需在实施初始标记之外访问网站或应用程序的源代码。AppMeasurement 和 Web SDK 均可使用扩展。

Adobe Analytics 可以收集以下类型的数据：

| 数据类型 | 详细信息 | 包含此数据的示例变量 |
| --- | --- | --- |
| 您网站上网页的页面名称或 URL | Adobe Analytics 需要这些数据才能运行。每次点击都需要一个 URL 或页面名称。 | [页面](/help/components/dimensions/page.md)，[页面 URL](/help/components/dimensions/page-url.md) |
| 基于时间的数据 | Adobe Analytics 需要这些数据才能运行。数据采集需要时间戳，基于时间的数据是从时间戳派生的。 | [在页面上停留的时间](/help/components/dimensions/time-spent-on-page.md)、[一天中的时间](/help/components/dimensions/hour-of-day.md)、[上午/下午](/help/components/dimensions/am-pm.md)、[工作日/周末](/help/components/dimensions/weekday-weekend.md)、[一周中的日子](/help/components/dimensions/day-of-week.md)、[一年中的月份](/help/components/dimensions/month-of-year.md) |
| 反向链接数据 | 当访客到达您的网站时，数据收集库会默认收集引用 URL。您可以自定义实施，以收集反向链接查询字符串中的数据。这种做法在营销活动和跟踪广告效果中很常见。 | [反向链接](/help/components/dimensions/referrer.md)，[反向链接域](/help/components/dimensions/referring-domain.md) |
| 匿名访客 ID | 数据收集库为访问您网站的每个浏览器生成并引用访客 ID。此 ID 存储在 Cookie 中。如果数据收集库无法设置 Cookie 标识符，则该库将会使用匿名访客标识的回退方法。此方法涉及使用访客的 IP 地址和用户代理字符串将相关点击与同一访问联系起来。如果您的组织已启用 IP 模糊处理，则会遵守此设置。请参阅 [Adobe Analytics 和浏览器 Cookie](../cookies/cookies.md)，了解更多信息。 | [独特访客](/help/components/metrics/unique-visitors.md) |
| 可识别的访客 ID | Adobe 不会自动收集自定义访客 ID。但是，您可以通过对您的实施进行自定义来收集这些数据。 | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| 外部搜索词 | 外部搜索数据包括来自搜索引擎的关键词。数据收集库根据引用的 URL 查找这些数据。然而，许多现代搜索引擎不再包含这些信息。 | [搜索关键词](/help/components/dimensions/search-keyword.md) |
| 内部搜索词 | 内部搜索数据包括来自您的网站或应用程序搜索功能的关键字。Adobe 不会自动收集内部搜索数据。但是，您可以通过对您的实施进行自定义来收集这些数据。对于使用 Adobe Analytics 的组织来说，这种做法很常见。 | [eVar](/help/components/dimensions/evar.md) |
| 计算机和浏览器规格 | 数据收集库会自动收集低熵浏览器提示，例如浏览器类型、操作系统类型以及设备是台式机还是移动设备。需要自定义配置来收集高熵提示，例如浏览器的特定版本、设备型号或操作系统版本。请参阅[客户端提示概述](../client-hints.md)，了解更多信息。 | [浏览器](/help/components/dimensions/browser.md)、[操作系统](/help/components/dimensions/operating-systems.md)、[移动设备维度](/help/components/dimensions/mobile-dimensions.md)、[显示器分辨率](/help/components/dimensions/monitor-resolution.md) |
| 地理位置信息 | Adobe 通过将 IP 地址的最后一个八位字节设置为 0，提供了阻止详细地理位置的功能。这会使地理信息不太精确，并且可以在[报表包设置](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)中进行设置。 | [城市](/help/components/dimensions/cities.md)、[区域](/help/components/dimensions/regions.md)、[国家/地区](/help/components/dimensions/countries.md) |
| IP 地址 | Adobe 在存储这些数据时提供了模糊（哈希）或完全删除访客 IP 地址的功能。EMEA 客户默认情况下通常会对 IP 地址设置进行模糊处理。无论模糊设置如何，IP 地址在 Analysis Workspace 中都不可用作维度；它仅包含在[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)中。请参阅管理员指南中的[常规帐户设置](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)，了解有关可用的模糊设置的详细信息。 | 无 |
| 您网站上提供的表单信息 | 所有实施类型都需要通过配置来收集这些数据。您可以将此数据包含在自定义变量中。 | [eVar](/help/components/dimensions/evar.md) |
| 点击您网站上的广告或链接 | 如果启用了 [`trackExternalLinks`](/help/implement/vars/config-vars/trackexternallinks.md) 或 [`trackDownloadLinks`](/help/implement/vars/config-vars/trackdownloadlinks.md)，则收集。当您启用 Activity Map 时，可以获得其他信息，如点击的位置。 | [Activity Map](/help/analyze/activity-map/overview.md)，[退出链接](/help/components/dimensions/exit-link.md)，[下载链接](/help/components/dimensions/download-link.md) |
| 在您的网站上购买的产品 | 所有实施类型都需要通过配置来收集这些数据。Adobe 提供了几个默认变量来收集这些信息。 | [产品](/help/components/dimensions/product.md)，[订单](/help/components/metrics/orders.md)，[收入](/help/components/metrics/revenue.md) |

{style="table-layout:auto"}

有关 Adobe 可能收集数据的更多变量，请参阅[维度概述](/help/components/dimensions/overview.md)和[量度概述](/help/components/metrics/overview.md)下的导航菜单。

## 数据处理位置

Adobe 为 Adobe Analytics 维护三个数据处理位置。这些站点会接收原始数据，并将其处理成报表包，该报表包针对数据存储和报告检索进行了优化。这些数据处理地点目前位于美国（俄勒冈州）、英国（伦敦）和新加坡。有关详细信息，请参阅[Adobe Analytics安全概述](https://www.adobe.com/cn/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank}。
