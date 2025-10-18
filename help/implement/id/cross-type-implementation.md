---
title: 跨不同的实施类型跟踪
description: 使用不同的实施类型并在不同实施类型之间无缝跟踪访客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 64%

---

# 跨不同的实施类型跟踪

Adobe Analytics 实施的核心架构在所有实施类型中都是一致的。此过程需要定义变量并将这些变量编译到一个图像请求中，然后将请求发送到 Adobe 数据收集服务器。此概念意味着，您可以跨同一站点的不同页面在 AppMeasurement、Web SDK 以及它们在 Adobe Experience Platform 数据收集中各自的扩展之间无缝切换。

Adobe 建议通过在所有页面使用相同的实施类型来保持站点实施的一致性。但是，如果您的网站的某些部分有不同的要求，则可以使用此页面来帮助确保在各页面之间持续跟踪访客。

如果您使用多种类型的实施(例如AppMeasurement和硬编码图像请求)，请确保正确设置以下变量并彼此匹配。

>[!NOTE]
>
>所有实施类型必须使用相同的访客标识类型（旧版Analytics ID或访客ID服务）。 Adobe建议尽可能在所有实施中使用访客ID服务。

| 变量 | AppMeasurement | Analytics 扩展 | Web SDK(Alloy) | Web SDK 标记扩展 | 硬编码图像请求 |
| --- | --- | --- | --- | --- | --- |
| 报告包 ID | [`s_gi`](../vars/functions/s-gi.md)中的字符串参数 | [配置扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=zh-Hans)时的[!UICONTROL 库管理]部分下的[!UICONTROL 报告包] | [配置数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans)时添加 Adobe Analytics 作为服务 | [配置数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans)时添加 Adobe Analytics 作为服务 | URL `pathname` 的一部分（`/b/ss/` 之后） |
| Experience Cloud ID 服务 | 实施 [`VisitorAPI.js`](appmeasurement.md) | 使用[Experience Cloud ID服务扩展](analytics-extension.md) | [本机包含](alloy.md) | [本机包含](web-sdk-extension.md) | 单独调用[ID服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=zh-Hans)以获取所需的ID，并在查询字符串中包含`mid` |
| Edge域 | [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md)变量 | 当[!UICONTROL 配置扩展]时，位于[!UICONTROL 常规]部分下的[SSL跟踪服务器](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=zh-Hans) | [配置 Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans) 时的 `edgeDomain` 属性 | [!UICONTROL 配置扩展时]Edge域[字段](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hans) | 图像请求 URL 的 `hostname` |

如果这些变量中的任何一个在跨实施类型中不一致，Adobe 会将它们视为不同的访客。如果未在您的网站上对访客进行跨实施类型无缝跟踪，则最常见的原因是 ID Service 配置不正确。确保每个实现类型在整个网站上正确获取相同的Experience Cloud ID (`mid`)。
