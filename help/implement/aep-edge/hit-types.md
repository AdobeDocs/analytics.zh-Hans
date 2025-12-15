---
title: Adobe Analytics中的Edge Network事件类型
description: Adobe Analytics如何解释从Edge Network接收的事件。
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 20%

---

# Adobe Analytics中的Edge Network事件类型

Adobe Analytics根据您在AppMeasurement中调用的函数来处理点击量不同。 例如，[`s.t`](/help/implement/vars/functions/t-method.md)和[`s.tl`](/help/implement/vars/functions/tl-method.md)包含或省略某些维度，并以不同的方式递增[页面查看次数](/help/components/metrics/page-views.md)。 Adobe Experience Platform仅包含[`sendEvent`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/js/commands/sendevent/overview)命令。 [`xdm`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/js/commands/sendevent/xdm)或[`data`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/js/commands/sendevent/data)有效负载中的特定属性决定了如何在Adobe Analytics中解释该数据。

Edge Network使用以下逻辑来确定Adobe Analytics [页面查看次数](/help/components/metrics/page-views.md)和[链接事件](/help/components/metrics/page-events.md)：

## 使用`xdm`对象的页面查看次数和链接事件

| XDM 负载包含... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL`，并且没有 `xdm.web.webInteraction.type` | 将负载视为&#x200B;**页面视图** |
| `xdm.eventType = web.webpagedetails.pageViews` | 将负载视为&#x200B;**页面视图** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL`) | 将有效负载视为&#x200B;**链接事件** <br/>还将`xdm.web.webPageDetails.name`和`xdm.web.webPageDetails.URL`设置为`null` |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webInteraction.name` 或 `xdm.web.webInteraction.URL`) | 将有效负载视为&#x200B;**链接事件** <br/>同时将`xdm.web.webPageDetails.name`和`xdm.web.webPageDetails.URL`设置为`null`（如果存在） |
| 无`xdm.web.webInteraction.type`，无`xdm.web.webPageDetails.name`，无`xdm.web.webPageDetails.URL` | 丢弃负载并忽略数据 |

>[!TIP]
>
>有效负载中的XDM字段名称区分大小写（例如，`webPageDetails.URL`）。 `xdm.eventType`字段是一个字符串值，它自己有一组接受值，这些值中的大小写可能与XDM字段名称不匹配。 有关接受的值，请参阅`eventType`XDM ExperienceEvent类[中的](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/classes/experienceevent#eventType)字段。

+++使用`xdm`字段的最小页面查看次数

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

+++使用`xdm.eventType`的最小页面查看次数

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++使用推荐字段的最小链接事件

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

## 使用`data`对象的页面查看次数和链接事件

| 数据对象有效负载包含…… | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` 或 `data.__adobe.analytics.pageURL`，并且没有 `data.__adobe.analytics.linkType` | 将负载视为&#x200B;**页面视图** |
| `data.__adobe.analytics.linkType` 和 (`data.__adobe.analytics.linkName` 或 `data.__adobe.analytics.linkURL`) | 将有效负载视为&#x200B;**链接事件** <br/>还将`data.__adobe.analytics.pageName`和`data.__adobe.analytics.pageURL`设置为`null` |
| 无`data.__adobe.analytics.linkType`，无`data.__adobe.analytics.pageName`，无`data.__adobe.analytics.pageURL` | 丢弃负载并忽略数据 |

+++使用`data`字段的最小页面查看次数

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

+++使用`data`字段的最小链接事件

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
>如果您在同一有效负载中同时包含`xdm`对象和`data`对象，Adobe Analytics会为这两个对象检查各自的字段。

## A4T和决策相关事件

除了区分页面查看和链接事件之外，以下逻辑还确定某些决策事件是属于A4T还是被丢弃。

| XDM 负载包含... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` 和 `xdm._experience.decisioning` | 将有效负载视为&#x200B;**A4T**&#x200B;调用。 |
| `xdm.eventType = decisioning.propositionDisplay`而非`xdm._experience.decisioning` | 丢弃负载并忽略数据 |
| `xdm.eventType = decisioning.propositionInteract`和`xdm._experience.decisioning`，无`xdm.web.webInteraction.type` | 将有效负载视为&#x200B;**A4T**&#x200B;调用。 |
| `xdm.eventType = decisioning.propositionInteract`且无`xdm._experience.decisioning`且无`xdm.web.webInteraction.type` | 丢弃有效负载并忽略数据。 |
| `xdm.eventType = decisioning.propositionFetch` | 丢弃负载并忽略数据 |

>[!TIP]
>
>以下`eventType`值已被弃用。 请注意，这些值对逻辑的影响方式与当前对应值相同：
>
>* 事件类型`display`已弃用。 请改用 `decisioning.propositionDisplay`。
>* 事件类型`click`已弃用。 请改用 `decisioning.propositionInteract`。
>* 事件类型`personalization.request`已弃用。 请改用 `decisioning.propositionFetch`。

+++最小化A4T显示

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

+++最小A4T交互

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

请参阅 [Adobe Analytics ExperienceEvent Full Extension 架构字段组](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)，了解更多信息。
