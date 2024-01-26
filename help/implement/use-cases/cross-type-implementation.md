---
title: 跨不同的实施类型跟踪
description: 使用不同的实施类型并在不同实施类型之间无缝跟踪访客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 100%

---

# 跨不同的实施类型跟踪

Adobe Analytics 实施的核心架构在所有实施类型中都是一致的。此过程需要定义变量并将这些变量编译到一个图像请求中，然后将请求发送到 Adobe 数据收集服务器。此概念意味着，您可以跨同一站点的不同页面在 AppMeasurement、Web SDK 以及它们在 Adobe Experience Platform 数据收集中各自的扩展之间无缝切换。

Adobe 建议通过在所有页面使用相同的实施类型来保持站点实施的一致性。但是，如果您的网站的某些部分有不同的要求，则可以使用此页面来帮助确保在各页面之间持续跟踪访客。

如果您使用多种类型的实施（例如 AppMeasurement 和硬编码图像请求），请确保正确设置以下变量并且这些变量相互匹配：

| 变量 | AppMeasurement | Analytics 扩展 | Web SDK | Web SDK 扩展 | 硬编码图像请求 |
| --- | --- | --- | --- | --- | --- |
| 报告包 ID | [`s_gi`](../vars/functions/s-gi.md) 中的字符串变量 | [配置扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=zh-Hans)时的[!UICONTROL 库管理]部分下的[!UICONTROL 报告包] | [配置数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans)时添加 Adobe Analytics 作为服务 | [配置数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans)时添加 Adobe Analytics 作为服务 | URL `pathname` 的一部分（`/b/ss/` 之后） |
| 跟踪服务器 | [`trackingServer`](../vars/config-vars/trackingserver.md) 和 [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 变量 | [配置扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=zh-Hans)时的[!UICONTROL 常规]部分下的[!UICONTROL 跟踪服务器]和[!UICONTROL SSL 跟踪服务器] | [配置 Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans) 时的 `edgeDomain` 属性 | [配置扩展](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hans)时的[!UICONTROL 边缘域] | 图像请求 URL 的 `hostname` |
| Experience Cloud ID 服务 | 实施 [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hans) | 使用 [Adobe Experience Cloud ID Service 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=zh-Hans) | 使用 [Adobe Experience Cloud ID Service 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=zh-Hans) | 使用 [Adobe Experience Cloud ID Service 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=zh-Hans) | [单独调用 ID Service 服务器](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=zh-Hans)以获取所需 ID |

{style="table-layout:auto"}

如果这些变量中的任何一个在跨实施类型中不一致，Adobe 会将它们视为不同的访客。如果未在您的网站上对访客进行跨实施类型无缝跟踪，则最常见的原因是 ID Service 配置不正确。请参阅 ID Service 用户指南中的[实施方法](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html?lang=zh-Hans)，了解详细信息。
