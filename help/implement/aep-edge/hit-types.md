---
title: Adobe Analytics中的Edge Network事件类型
description: Adobe Analytics如何解释从Edge Network接收的事件。
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 8d369bd3be3ae9c075e490e108666728a2cff5dc
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 28%

---

# Adobe Analytics中的Edge Network事件类型

Adobe Analytics根据您在AppMeasurement中调用的函数来处理点击量不同。 例如，[`s.t`](/help/implement/vars/functions/t-method.md)和[`s.tl`](/help/implement/vars/functions/tl-method.md)包含或省略某些维度，并以不同的方式递增页面查看。 Adobe Experience Platform仅包含`sendEvent`命令。 `xdm`有效负载中的特定属性确定如何在Adobe Analytics中解释该数据。

Edge Network使用以下逻辑来确定Adobe Analytics页面查看次数和链接事件：

| XDM 负载包含... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL`，并且没有 `xdm.web.webInteraction.type` | 将负载视为&#x200B;**页面视图** |
| `xdm.eventType = web.webPageDetails.pageViews` | 将负载视为&#x200B;**页面视图** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webInteraction.name` 或 `xdm.web.webInteraction.url`) | 将负载视为&#x200B;**链接事件** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.url`) | 将有效负载视为&#x200B;**链接事件** <br/>还将`xdm.web.webPageDetails.name`和`xdm.web.webPageDetails.URL`设置为`null` |
| 无 `xdm.web.webInteraction.type` 和（无 `xdm.webPageDetails.name` 且无 `xdm.web.webPageDetails.URL`） | 丢弃负载并忽略数据 |

除了区分页面查看次数和链接点击次数外，还遵循以下逻辑来确定某些事件是属于A4T还是被放弃。

| XDM 负载包含... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display`或<br/>`xdm.eventType = decisioning.propositionDisplay`或<br/>`xdm.eventType = personalization.request`或<br/>`xdm.eventType = decisioning.propositionFetch`和`xdm._experience.decisioning` | 将有效负载视为&#x200B;**A4T**&#x200B;调用。 |
| `xdm.eventType = display`、<br/>`xdm.eventType = decisioning.propositionDisplay`、<br/>`xdm.eventType = personalization.request`或<br/>`xdm.eventType = decisioning.propositionFetch`且没有`xdm._experience.decisioning` | 丢弃负载并忽略数据 |
| `xdm.eventType = click`或`xdm.eventType = decisioning.propositionInteract`和`xdm._experience.decisioning`，无`web.webInteraction.type` | 将有效负载视为&#x200B;**A4T**&#x200B;调用。 |
| `xdm.eventType = click`或`xdm.eventType = decisioning.propositionInteract`，没有`xdm._experience.decisioning`和没有`web.webInteraction.type` | 丢弃有效负载并忽略数据。 |

请参阅 [Adobe Analytics ExperienceEvent Full Extension 架构字段组](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)，了解更多信息。
