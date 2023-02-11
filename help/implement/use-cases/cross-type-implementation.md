---
title: 跨不同的实施类型跟踪
description: 使用不同的实施类型并在不同实施类型之间无缝跟踪访客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 14%

---

# 跨不同的实施类型跟踪

Adobe Analytics实施的核心架构在所有实施类型中都保持一致。 该过程包括定义变量并将它们编译到一个图像请求中，该图像请求将发送到Adobe的数据收集服务器。 此概念意味着，您可以在Adobe Experience Platform数据收集中的AppMeasurement、Web SDK及其各自的扩展之间，在同一网站的不同页面之间无缝切换。

Adobe建议在所有页面中使用相同的实施类型，以保持网站实施之间的一致性。 但是，如果网站的某些部分有不同的要求，您可以使用此页面帮助确保在不同页面之间始终如一地跟踪访客。

如果您使用多种类型的实施（如AppMeasurement和硬编码图像请求），请确保正确设置了以下变量并且它们彼此匹配：

| 变量 | AppMeasurement | Analytics 扩展 | Web SDK | Web SDK 扩展 | 硬编码图像请求 |
| --- | --- | --- | --- | --- | --- |
| 报告包 ID | 中的字符串参数 [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL 报表包] 下 [!UICONTROL 库管理] 部分 [配置扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | 将Adobe Analytics添加为服务 [配置数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | 将Adobe Analytics添加为服务 [配置数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | URL的一部分 `pathname` （之后） `/b/ss/`) |
| 跟踪服务器 | 的 [`trackingServer`](../vars/config-vars/trackingserver.md) 和 [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 变量 | [!UICONTROL 跟踪服务器] 和 [!UICONTROL SSL跟踪服务器] 下 [!UICONTROL 常规] 部分 [配置扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | 的 `edgeDomain` 属性 [配置Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans) | 的 [!UICONTROL 边缘域] when [配置扩展](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) | 的 `hostname` 图像请求URL的 |
| Experience Cloud ID 服务 | 实施 [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hans) | 使用 [Adobe Experience Cloud ID服务扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | 使用 [Adobe Experience Cloud ID服务扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | 使用 [Adobe Experience Cloud ID服务扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | 制作 [对ID服务服务器的单独调用](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) 以获取所需的ID |

{style=&quot;table-layout:auto&quot;}

如果这些变量中的任何一个在每种实施类型中不一致，则Adobe会将它们视为单独的访客。 如果无法在您网站上的各种实施类型中无缝跟踪访客，则最常见的原因是ID服务配置不正确。 请参阅 [实施方法](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) （详细信息）。
