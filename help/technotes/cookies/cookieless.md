---
title: 减轻浏览器 Cookie 限制影响的选项
description: 了解如何减轻浏览器 Cookie 限制的影响以改进 Adobe Analytics 的数据收集。
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 51%

---


# 减轻浏览器 Cookie 限制影响的选项

本文档讨论了在主要浏览器为Cookie实施跟踪预防措施时，用于在资产和解决方案之间保留永久访客标识的选项。

Adobe Analytics 依靠第一方 Cookie 记录访客在网站上的活动。Analytics 还依靠第三方 Cookie 了解访客的站外活动，例如在您拥有的其他域上的活动。许多浏览器上阻止了第三方 Cookie，并且随着 Chrome 即将到来的停止支持（目前计划于 2022 年）将大量地不可用。所有浏览器上允许第一方 Cookie，但根据 Apple 的 [ITP 跟踪预防](https://webkit.org/tracking-prevention)措施，在 Safari 和其他浏览器上具有有限的失效期。有关浏览器Cookie当前限制的更多信息，请参阅[Adobe Analytics和浏览器Cookie](cookies.md)。

这些浏览器限制反映了一个更广泛的趋势，即从匿名第三方跟踪转向用户与他们所信任品牌之间明确的信息共享。为了支持这种转变，Adobe 为客户提供了方法来补充传统 Cookie，这种方法是包括通过其第一方关系收集的持久标识符。

## Customer Journey Analytics 和 Cross Device Analytics

[Adobe客户](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans) 历程 [分析](/help/components/cda/overview.md) 和跨设备分析用户，除了Cookie之外，还可包含持久标识符（如经过哈希处理的登录）。这使您能够了解跨设备以及跨在线和离线渠道(如果是Customer Journey Analytics)的客户历程：

* **客户历程** 分析基于Adobe Experience Platform构建，可根据任何通用的客户ID，灵活地在Analysis Workspace中组合在线和离线数据。您可以指定要用于任何给定分析的ID，并在Analysis Workspace中浏览数据。 Analytics Select、Prime和Ultimate客户有资格将其作为附加产品购买。

* **跨设备分** 析是对传统Adobe Analytics的一项增强，它允许客户为访客使用替代标识符。此功能允许您从以设备为中心的视图转变为以人员为中心的视图。 跨设备分析适用于Analytics Ultimate客户。

## 服务器端数据收集

服务器端收集提供了灵活性，让您可以提供自己的标识符而不是依靠浏览器机制来设置 Cookie。

您可以使用[数据插入API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md)或[批量数据插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)将数据提交到Analytics服务器端。 建议对新的服务器端实施使用批量数据插入API。 有关两个 API 的比较，请参阅“[我应该使用哪个 Adobe Analytics 工具](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html?lang=zh-Hans)。”

## 更多信息

有关您的企业从第三方Cookie转移到其他位置的实际步骤，请参阅[通过Adobe](https://business.adobe.com/solutions/cookieless.html)获取并保持客户处于无Cookie世界中，以及深入的[在第三方Cookie之外思考：没有第三方Cookie的世界的完整指南](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)。”

>[!MORELIKETHIS]
[Adobe Analytics 和浏览器 Cookie](cookies.md)>
>
