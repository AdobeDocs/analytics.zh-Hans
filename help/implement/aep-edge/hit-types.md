---
title: Adobe Analytics 中的 Edge Network 事件类型
description: Adobe Analytics 如何解读从 Edge Network 接收的事件。
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 100%

---

# Adobe Analytics 中的 Edge Network 事件类型

Adobe Analytics 根据您在 AppMeasurement 中调用了哪些函数而对点击进行不同的处理。例如，[`s.t`](/help/implement/vars/functions/t-method.md) 和 [`s.tl`](/help/implement/vars/functions/tl-method.md) 包含或略去某些维度，以不同的方式增加[页面浏览量](/help/components/metrics/page-views.md)。Adobe Experience Platform 仅包含 [`sendEvent`](https://experienceleague.adobe.com/cn/docs/experience-platform/collection/js/commands/sendevent/overview) 命令。[`xdm`](https://experienceleague.adobe.com/cn/docs/experience-platform/collection/js/commands/sendevent/xdm) 或 [`data`](https://experienceleague.adobe.com/cn/docs/experience-platform/collection/js/commands/sendevent/data) 负载中的特定属性决定了 Adobe Analytics 如何解读这些数据。

Edge Network 使用以下逻辑来确定 Adobe Analytics [页面浏览量](/help/components/metrics/page-views.md)和[链接事件](/help/components/metrics/page-events.md)：

## 使用 `xdm` 对象的页面浏览量和链接事件

| XDM 负载包含... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL`，并且没有 `xdm.web.webInteraction.type` | 将负载视为&#x200B;**页面视图** |
| `xdm.eventType = web.webpagedetails.pageViews` | 将负载视为&#x200B;**页面视图** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL`) | 将负载视为&#x200B;**链接事件** <br/>还将 `xdm.web.webPageDetails.name` 和 `xdm.web.webPageDetails.URL` 设置为 `null` |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webInteraction.name` 或 `xdm.web.webInteraction.URL`) | 将负载视为&#x200B;**链接事件** <br/>还将 `xdm.web.webPageDetails.name` 和 `xdm.web.webPageDetails.URL` 设置为 `null`（如果存在） |
| 无 `xdm.web.webInteraction.type`，无 `xdm.web.webPageDetails.name`，无 `xdm.web.webPageDetails.URL` | 丢弃负载并忽略数据 |

>[!TIP]
>
>负载中的 XDM 字段名称区分大小写（例如 `webPageDetails.URL`）。`xdm.eventType` 字段是一个字符串值，它自己有一组可接受的值，这些值的大小写可能与 XDM 字段名称不匹配。有关可接受的值请参阅 [XDM ExperienceEvent 类](https://experienceleague.adobe.com/cn/docs/experience-platform/xdm/classes/experienceevent#eventType)中的 `eventType` 字段。

+++使用 `xdm` 字段的最少页面浏览量

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++使用 `xdm.eventType` 的最少页面浏览量

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++使用推荐字段的最少链接事件

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## 使用 `data` 对象的页面浏览量和链接事件

| 数据对象负载包含… | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` 或 `data.__adobe.analytics.pageURL`，并且没有 `data.__adobe.analytics.linkType` | 将负载视为&#x200B;**页面视图** |
| `data.__adobe.analytics.linkType` 和 (`data.__adobe.analytics.linkName` 或 `data.__adobe.analytics.linkURL`) | 将负载视为&#x200B;**链接事件** <br/>还将 `data.__adobe.analytics.pageName` 和 `data.__adobe.analytics.pageURL` 设置为 `null` |
| 无 `data.__adobe.analytics.linkType`，无 `data.__adobe.analytics.pageName`，无 `data.__adobe.analytics.pageURL` | 丢弃负载并忽略数据 |

+++使用 `data` 字段的最少页面浏览量

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++使用 `data` 字段的最少链接事件

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>如果您在同一负载中同时包含 `xdm` 对象和 `data` 对象，Adobe Analytics 就会检查这两个对象的相应字段。

## A4T 和决策相关事件

除了区分页面浏览量和链接事件之外，以下逻辑还决定了特定的决策事件是归类于 A4T 还是被丢弃。

| XDM 负载包含... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` 和 `xdm._experience.decisioning` | 将负载视为 **A4T** 调用。 |
| `xdm.eventType = decisioning.propositionDisplay`，无 `xdm._experience.decisioning` | 丢弃负载并忽略数据 |
| `xdm.eventType = decisioning.propositionInteract` 和 `xdm._experience.decisioning`，无 `xdm.web.webInteraction.type` | 将负载视为 **A4T** 调用。 |
| `xdm.eventType = decisioning.propositionInteract`，无 `xdm._experience.decisioning`，无 `xdm.web.webInteraction.type` | 丢弃负载并忽略数据。 |
| `xdm.eventType = decisioning.propositionFetch` | 丢弃负载并忽略数据 |

>[!TIP]
>
>以下 `eventType` 值已弃用。请注意，这些值与它们当前的对应值对逻辑的影响相同：
>
>* 事件类型 `display` 已弃用。请改用 `decisioning.propositionDisplay`。
>* 事件类型 `click` 已弃用。请改用 `decisioning.propositionInteract`。
>* 事件类型 `personalization.request` 已弃用。请改用 `decisioning.propositionFetch`。

+++最少 A4T 显示

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++最少 A4T 交互

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

请参阅 [Adobe Analytics ExperienceEvent Full Extension 架构字段组](https://experienceleague.adobe.com/cn/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)，了解更多信息。
