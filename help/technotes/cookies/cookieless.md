---
title: 减轻浏览器 Cookie 限制影响的选项
description: 了解如何减轻浏览器 Cookie 限制的影响以改进 Adobe Analytics 的数据收集。
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 99%

---

# 减轻浏览器 Cookie 限制影响的选项

本文档讨论在主流浏览器实施针对 Cookie 的跟踪预防措施时，跨属性和解决方案保留持久性访客识别的选项。

Adobe Analytics 依靠第一方 Cookie 记录访客在网站上的活动。Analytics 还依靠第三方 Cookie 了解访客的站外活动，例如在您拥有的其他域上的活动。许多浏览器上阻止了第三方 Cookie，并且随着 Chrome 即将停止支持（目前计划于 2024 年底），大量第三方 Cookie 将不可用。 所有浏览器上允许第一方 Cookie，但根据 Apple 的 [ITP 跟踪预防](https://webkit.org/tracking-prevention)措施，在 Safari 和其他浏览器上具有有限的失效期。有关对浏览器 Cookie 当前限制的更多信息，请参阅 [Adobe Analytics 和浏览器 Cookie](cookies.md)。

这些浏览器限制反映了一个更广泛的趋势，即从匿名第三方跟踪转向用户与他们所信任品牌之间明确的信息共享。为了支持这种转变，Adobe 为客户提供了方法来补充传统 Cookie，这种方法是包括通过其第一方关系收集的持久标识符。

## Customer Journey Analytics 和 Cross Device Analytics

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans) 和 [Cross-Device Analytics](/help/components/cda/overview.md) 允许用户在 Cookie 之外包括持久标识符（例如哈希登录）。这样，您可以跨设备了解客户历程，如果是 Customer Journey Analytics，还可以跨在线和离线渠道了解客户历程：

* **Customer Journey Analytics** 基于 Adobe Experience Platform 构建，并提供基于任何通用客户 ID 在 Analysis Workspace 中组合在线和离线数据的灵活性。您可以指定要用于任何给定分析的 ID，并在 Analysis Workspace 中浏览数据。Analytics Select、Prime 和 Ultimate 客户有资格购买此附加产品。

* **Cross-Device Analytics** 是对传统 Adobe Analytics 的增强，允许客户使用替代标识符进行访问。此功能允许您从以设备为中心的视图移动到以人员为中心的视图。Analytics Ultimate 客户可以使用 Cross-Device Analytics。

## 服务器端数据收集

服务器端收集提供了灵活性，让您可以提供自己的标识符而不是依靠浏览器机制来设置 Cookie。

您可以使用 [Data Insertion API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) 或 [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) 将数据提交到 Analytics 服务器端。建议将 Bulk Data Insertion API 用于新服务器端实施。有关两个 API 的比较，请参阅“[我应该使用哪个 Adobe Analytics 工具](/help/analyze/get-started/which-analytics-tool.md)”。

## 带 Web SDK 的第一方设备 ID (FPID)

利用 Adobe Experience Platform Web SDK，您可以选择设置和管理您自己的设备标识符，而不是 Adobe 生成的 Experience Cloud ID (ECID)。这些被称为第一方设备 ID (FPID)。在[此处](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=zh-Hans)了解详情。

## 更多信息

有关您的企业为摆脱第三方 Cookie 可以采取的可行步骤，请参阅[使用 Adobe 在无 Cookie 的世界中获取和保留客户](https://business.adobe.com/cn/solutions/cookieless.html)和深入的[超越第三方 Cookie 思考：没有第三方 Cookie 的完整世界指南](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)。

>[!MORELIKETHIS]
>
>[Adobe Analytics 和浏览器 Cookie](cookies.md)
