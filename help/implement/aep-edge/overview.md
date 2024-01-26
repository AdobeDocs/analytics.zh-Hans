---
title: 使用 Adobe Experience Platform Edge 实施 Adobe Analytics
description: 在 Adobe Analytics 中使用源自 Experience Platform 的 XDM 数据概述
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 37%

---

# 使用 Adobe Experience Platform Edge 实施 Adobe Analytics

Adobe Experience Platform Edge 允许您将发送到多个产品的数据发送到一个集中的位置。 Experience Edge 将适当的信息转发给所需的产品。 此概念允许您整合实施工作，尤其是跨多个数据解决方案进行整合。

Adobe 提供了三种向 Experience Edge 发送数据的主要方式：

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：使用 Adobe Experience Platform 数据收集中的 Web SDK 扩展将数据发送到 Edge。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：使用 Adobe Experience Platform 数据收集中的 Mobile SDK 扩展将数据发送到 Edge。
* **[Adobe Experience Platform Edge Network服务器API](server-api/overview.md)**：使用API直接将数据发送到Edge。



## Adobe Analytics如何处理Experience Edge数据

发送到Experience Edge的数据必须符合基于 [XDM（体验数据模型）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans). XDM让您灵活地定义作为事件一部分的字段。 当事件到达Adobe Analytics时，这些事件将转换为Adobe Analytics可以处理的更结构化数据：页面查看或链接事件。

XDM本身没有规定如何定义页面查看或链接事件，也没有指示Adobe Analytics如何处理其有效负载。 例如，某些开箱即用的XDM字段似乎与页面查看或链接事件相关，例如 `eventType`， `web.webPageDetails.pageViews`，或 `web.webInteraction.linkEvents` 与实施完全无关，并且与Adobe Analytics无关。

要正确处理页面查看次数和链接事件，将对发送到AdobeExperience Edge网络并转发到Adobe Analytics的数据应用以下逻辑。

| XDM有效负载包含…… | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` 或 `web.webPageDetails.URL` 而无 `web.webInteraction.type` | 将有效负载视为 **页面查看** |
| `web.webInteraction.type` 和(`web.webInteraction.name` 或 `web.webInteraction.url`) | 将有效负载视为 **链接事件** |
| `web.webInteraction.type` 和(`web.webPageDetails.name` 或 `web.webPageDetails.url`) | 将有效负载视为 **链接事件** <br/>`web.webPageDetails.name` 和 `web.webPageDetails.URL` 设置为 `null` |
| 否 `web.webInteraction.type` 和(否 `webPageDetails.name` 而无 `web.webPageDetails.URL`) | 丢弃有效负载并忽略数据 |

{style="table-layout:auto"}

