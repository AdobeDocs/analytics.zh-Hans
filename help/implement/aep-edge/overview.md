---
title: 使用 Adobe Experience Platform Edge 实施 Adobe Analytics
description: 在 Adobe Analytics 中使用源自 Experience Platform 的 XDM 数据概述
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 4453c2aa2ea70ef4d00b2bc657285287f3250c65
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 85%

---

# 使用 Adobe Experience Platform Edge Network 实施 Adobe Analytics

Adobe Experience Platform Edge Network 允许您将发送到多个产品的数据发送到一个集中的位置。 Edge Network 将适当的信息转发给所需的产品。 此概念允许您整合实施工作，尤其是跨多个数据解决方案进行整合。

Adobe 提供了三种向 Edge Network 发送数据的主要方式：

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：使用 Adobe Experience Platform 数据收集中的 Web SDK 扩展将数据发送到 Edge。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：使用 Adobe Experience Platform 数据收集中的 Mobile SDK 扩展将数据发送到 Edge。
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**：使用 API 直接向 Edge 发送数据。



## Adobe Analytics 处理 Edge Network 数据的方式

发送到 Adobe Experience Platform Edge Network 的数据可以采用两种格式：

* XDM 对象：符合基于 [XDM（体验数据模型）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)的架构。 XDM 可让您灵活地将字段定义为事件的一部分。事件到达 Adobe Analytics 时，会被转换为 Adobe Analytics 可以处理的格式。
* 数据对象：使用映射到 Adobe Analytics 的特定字段向 Edge Network 发送数据。 Edge Network 会检测这些字段的存在，并将其转发到 Adobe Analytics，而无需符合架构。

该Edge Network使用以下逻辑来确定Adobe Analytics页面查看次数和链接事件：

| XDM 负载包含... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL`，并且没有 `xdm.web.webInteraction.type` | 将负载视为&#x200B;**页面视图** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webInteraction.name` 或 `xdm.web.webInteraction.url`) | 将负载视为&#x200B;**链接事件** |
| `web.webInteraction.type` 和 (`web.webPageDetails.name` 或 `web.webPageDetails.url`) | 将负载视为&#x200B;**链接事件**  <br/>`web.webPageDetails.name` 和 `web.webPageDetails.URL` 设置为 `null` |
| 无 `web.webInteraction.type` 和（无 `webPageDetails.name` 且无 `web.webPageDetails.URL`） | 丢弃负载并忽略数据 |
| `xdm.eventType = display`或<br/>`xdm.eventType = decisioning.propositionDisplay`或<br/>`xdm.eventType = personalization.request`或<br/>`xdm.eventType = decisioning.propositionFetch`和`xdm._experience.decisioning` | 将有效负载视为&#x200B;**A4T**&#x200B;调用。 |
| `xdm.eventType = display`、<br/>`xdm.eventType = decisioning.propositionDisplay`、<br/>`xdm.eventType = personalization.request`或<br/>`xdm.eventType = decisioning.propositionFetch`且没有`xdm._experience.decisioning` | 丢弃负载并忽略数据 |
| `xdm.eventType = click`或`xdm.eventType = decisioning.propositionInteract`和`xdm._experience.decisioning`，无`web.webInteraction.type` | 将有效负载视为&#x200B;**A4T**&#x200B;调用。 |
| `xdm.eventType = click`或`xdm.eventType = decisioning.propositionInteract`，没有`xdm._experience.decisioning`和没有`web.webInteraction.type` | 丢弃有效负载并忽略数据。 |

{style="table-layout:auto"}

请参阅 [Adobe Analytics ExperienceEvent Full Extension 模式字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html)，了解更多信息。
