---
title: 使用 Adobe Experience Platform Edge 实施 Adobe Analytics
description: 在 Adobe Analytics 中使用源自 Experience Platform 的 XDM 数据概述
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 50%

---

# 使用Adobe Experience Platform Edge Network实施Adobe Analytics

Adobe Experience Platform Edge Network允许您将发送到多个产品的数据发送到一个集中位置。 Edge Network将适当的信息转发给所需的产品。 此概念允许您整合实施工作，尤其是跨多个数据解决方案进行整合。

Adobe提供了三种向Edge Network发送数据的主要方式：

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：使用 Adobe Experience Platform 数据收集中的 Web SDK 扩展将数据发送到 Edge。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：使用 Adobe Experience Platform 数据收集中的 Mobile SDK 扩展将数据发送到 Edge。
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**：使用 API 直接向 Edge 发送数据。



## Adobe Analytics如何处理Edge Network数据

发送到Adobe Experience Platform Edge Network的数据可以遵循两种格式：

* XDM对象：符合基于的架构 [XDM（体验数据模型）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html). XDM 可让您灵活地将字段定义为事件的一部分。在事件到达Adobe Analytics时，它们会被转换为Adobe Analytics可以处理的格式。
* 数据对象：使用映射到Adobe Analytics的特定字段将数据发送到Edge Network。 边缘网络检测这些字段的存在，并将它们转发到Adobe Analytics而无需符合架构。


Edge Network使用以下逻辑来确定Adobe Analytics页面查看次数和链接事件

| XDM 负载包含... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` 或 `web.webPageDetails.URL`，并且没有 `web.webInteraction.type` | 将负载视为&#x200B;**页面视图** |
| `web.webInteraction.type` 和 (`web.webInteraction.name` 或 `web.webInteraction.url`) | 将负载视为&#x200B;**链接事件** |
| `web.webInteraction.type` 和 (`web.webPageDetails.name` 或 `web.webPageDetails.url`) | 将负载视为&#x200B;**链接事件**  <br/>`web.webPageDetails.name` 和 `web.webPageDetails.URL` 设置为 `null` |
| 无 `web.webInteraction.type` 和（无 `webPageDetails.name` 且无 `web.webPageDetails.URL`） | 丢弃负载并忽略数据 |

{style="table-layout:auto"}

请参阅 [Adobe Analytics ExperienceEvent Full Extension 模式字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html)，了解更多信息。
