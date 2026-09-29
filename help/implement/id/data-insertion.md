---
title: 使用数据插入API识别访客
description: 识别使用数据插入API进行服务器端和直接Adobe Analytics数据收集的访客。
feature: Implementation Basics
role: Admin, Developer, Leader
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%
---
# 使用数据插入API识别访客

[数据插入API](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)将点击发送到Adobe Analytics收集服务器，但没有客户端库，如AppMeasurement或Web SDK。 由于不存在可为您管理标识的库，因此您可以自行设置访客标识符 — 在浏览器中用于直接图像请求，或者在您的服务器上用于服务器端收集。

>[!NOTE]
>
>本页介绍访客身份。 有关生成和发送请求本身，请参阅Adobe Developer上的[数据插入API文档](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)。

Adobe使用标准[操作顺序](overview.md)标识访客： `vid`，然后是`aid`、`mid`、`fid`，最后是IP地址和用户代理。 使用数据插入API，您通常直接设置以下三个标识符之一：ECID (`mid`)、Analytics访客ID (`aid`)或自定义访客ID (`vid`)。

## 使用ECID（推荐）

ECID（作为`mid`发送）是在Adobe Analytics、Adobe Target和Adobe Audience Manager中共享的现代跨解决方案访客标识符。 Adobe建议尽可能使用它。

使用[访客ID服务](https://experienceleague.adobe.com/cn/docs/id-service/using/home) (`VisitorAPI.js`)获取ECID。 在浏览器中，使用[`getInstance`](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/id-service-api/methods/getinstance)以您的IMS组织ID初始化服务，然后使用[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/id-service-api/methods/getmcvid)读取ECID：

```js
var visitor = Visitor.getInstance("YOUR_ORG_ID@AdobeOrg");
var ecid = visitor.getMarketingCloudVisitorID();
```

在每次点击时将该值作为`mid`查询参数发送，并将您的IMS组织ID作为`mcorgid`参数发送，以便ECID正确解析。 如果您的数据转发到Audience Manager，则也从[`getLocationHint`](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/id-service-api/methods/getlocationhint)发送区域作为`aamlh`参数。 要将您自己的客户标识符与访客相关联，请使用[`setCustomerIDs`](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/id-service-api/methods/setcustomerids)。

对于服务器端收集，请在客户端获取ECID，并将其转发到您的服务器，以便在每次点击时发送。 若要在没有客户端的情况下完全在服务器端生成ECID，请使用ID服务的[直接集成](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/implementation/direct-integration)。

## 使用Analytics访客标识

Analytics访客ID (`aid`)存储在[`s_vi`](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/cookies/analytics) Cookie中。 当点击到达时没有标识符，收集服务器分配`aid`并尝试设置包含该标识符的Cookie。 某些[响应类型](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types)在响应正文中也包含此标识符。

* **客户端（直接图像请求）。** 浏览器存储服务器返回的`s_vi` Cookie，并在以后每次请求时将其发送到同一收集域。 随后会自动识别该访客，且无需自行设置`aid`。 由于此模型依赖于Cookie，因此其持久性限制与任何基于Cookie的标识相同。 请参阅使用AppMeasurement的[访客识别](appmeasurement.md)以了解第一方与第三方Cookie行为对比，并参阅[操作顺序](overview.md)以了解Adobe如何选择要使用的标识符。 Adobe建议使用ECID作为持久标识。

  >[!NOTE]
  >
  >如果您直接从`s_vi` Cookie读取访客ID，则Cookie会在附加数据（例如，`[CS]v1|<id>[CE]`）中封装该ID — 仅提取`<id>`部分。 从访客响应中读取ID将直接返回该ID，而无需解析。

* **服务器端。** 服务器没有Cookie Jar，因此您自己存储并重新发送`aid`，并将其作为用户的密钥：

  1. 查找用户存储的`aid`。
  1. 如果您有，请将其作为`aid`查询参数发送。
  1. 如果不包含，请发送不带标识符的点击，请求返回分配的`aid`的响应类型，然后将其存储以供下次使用。

  第一个无标识符点击已归因于服务器返回的`aid`，因此您在拥有ID之前发送数据，不会丢失任何数据。 对于返回ID （`3`用于JavaScript，`11`用于XML，`10`用于JSON）和请求格式的响应类型，请参阅数据插入API文档中的[响应类型](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types)。

  服务器端请求不携带访客Cookie，它自己的IP地址和用户代理属于发件人。 要正确归因点击，请同时转发访客的实际IP地址（`X-Forwarded-For`标头）和用户代理（`User-Agent`标头）。

## 使用自定义访客ID

如果您已经拥有完全控制的持久标识符，则可以在每次点击时以[`visitorID`](/help/implement/vars/config-vars/visitorid.md) (`vid`)的形式发送它，并且端到端地发送自己的标识。 这适用于提供稳定设备标识符的非浏览器平台。 例如，Unity应用程序可以将其设备标识符作为`vid`发送。

>[!IMPORTANT]
>
>仅在可保证每次点击时具有稳定值时才使用`vid`：
>
>* **浏览器不适合使用。** 浏览器没有持久标识符，无法可靠地填充该标识符，因此浏览器集`vid`容易出现碎片或冲突。 请改用基于Cookie的客户端模型。
>* **身份验证标识符要小心。** 用户登录之前没有标识符，如果用户注销，则以后的点击将归因于其他访客。 这些操作会将一个人的活动拆分为多个访客。

有关自定义访客ID的格式和约束，请参阅[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。
