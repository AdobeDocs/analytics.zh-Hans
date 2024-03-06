---
title: 使用 Adobe Experience Platform Edge 实施 Adobe Analytics
description: 在 Adobe Analytics 中使用源自 Experience Platform 的 XDM 数据概述
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 95%

---

# 使用 Adobe Experience Platform Edge 实施 Adobe Analytics

Adobe Experience Platform Edge 允许您将发送到多个产品的数据发送到一个集中的位置。 Experience Edge 将适当的信息转发给所需的产品。 此概念允许您整合实施工作，尤其是跨多个数据解决方案进行整合。

Adobe 提供了三种向 Experience Edge 发送数据的主要方式：

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：使用 Adobe Experience Platform 数据收集中的 Web SDK 扩展将数据发送到 Edge。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：使用 Adobe Experience Platform 数据收集中的 Mobile SDK 扩展将数据发送到 Edge。
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**：使用 API 直接向 Edge 发送数据。



## Adobe Analytics 处理 Experience Edge 数据的方式

发送到 Experience Edge 的数据必须符合基于 [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) 的架构。XDM 可让您灵活地将字段定义为事件的一部分。当事件到达 Adobe Analytics 时，这些事件将转换为 Adobe Analytics 可以处理的更加结构化的数据：页面视图或链接事件。

XDM 本身并未规定如何定义页面视图或链接事件，也不指示 Adobe Analytics 如何处理其负载。例如，某些看似与页面视图或链接事件相关的现成的 XDM 字段（例如 `eventType`、`web.webPageDetails.pageViews` 或 `web.webInteraction.linkEvents`）完全与实施无关，并且与 Adobe Analytics 无关。

要正确处理页面视图和链接事件，可将以下逻辑应用于发送到 Adobe Experience Edge Network 并转发到 Adobe Analytics 的数据。

| XDM 负载包含... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` 或 `web.webPageDetails.URL`，并且没有 `web.webInteraction.type` | 将负载视为&#x200B;**页面视图** |
| `web.webInteraction.type` 和 (`web.webInteraction.name` 或 `web.webInteraction.url`) | 将负载视为&#x200B;**链接事件** |
| `web.webInteraction.type` 和 (`web.webPageDetails.name` 或 `web.webPageDetails.url`) | 将负载视为&#x200B;**链接事件**  <br/>`web.webPageDetails.name` 和 `web.webPageDetails.URL` 设置为 `null` |
| 无 `web.webInteraction.type` 和（无 `webPageDetails.name` 且无 `web.webPageDetails.URL`） | 丢弃负载并忽略数据 |

{style="table-layout:auto"}

请参阅 [Adobe Analytics ExperienceEvent完整扩展架构字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) 以了解更多信息。
