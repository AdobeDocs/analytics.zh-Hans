---
title: 适用于Adobe Analytics的访客ID服务迁移注意事项
description: 概述Adobe Analytics如何与访客ID服务进行交互。
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# 适用于Adobe Analytics的访客ID服务迁移注意事项

如果您的组织计划使用现有的Analytics实施迁移到访客ID服务，则需要考虑一些重要主题。 这些注意事项对于保持访客识别完整性以及了解在存在现有Analytics实施的情况下ID服务如何运行非常重要。

## 访客ID服务如何与旧版Analytics访客Cookie进行交互

由于AppMeasurement具有其自身的访客识别方法，因此当组织部署访客ID服务时，某些访客可能会具有旧版Analytics Cookie。 下表概述了在不同情况下如何识别访客。

* **没有访客Cookie**： ID服务分配了一个Experience Cloud ID (`mid`)。
* **存在`s_vi` Cookie**：除Experience Cloud ID (`aid`)外，ID服务还将现有的旧版Analytics ID (`AMCV`)写入`mid` Cookie。 由于`aid`在[操作顺序](overview.md)中更高，在`AMCV` Cookie过期或被清除之前，旧版Analytics ID是访客标识符。 启用宽限期后，ID服务在其响应中同时包含`mid`和`aid`。
* **存在回退Cookie**： ID服务没有将回退Cookie (`fid`)写入`AMCV` Cookie。 相反，访客会收到Experience Cloud ID (`mid`)，就像他们是新访客一样。

## 访客ID服务宽限期

如果您有多个实施要将数据发送至同一报表包，并且您只能对某些实施实施实施访客ID服务，则Adobe建议配置一个宽限期。 例如，如果网站的支持部分由单独的标记解决方案管理，则您可能将访客ID服务部署在网站其他部分的支持部分之前。 如果没有宽限期，则查看支持部分的新访客会收到一个旧版Analytics访客ID，从而导致两个单独的访客被计数。 通过宽限期，访客ID服务会同时发出Experience Cloud ID (`mid`)和旧版Analytics访客ID (`aid`)，以便您网站中没有ID服务的区域在识别访客时保持一致。

如果您在网站的所有区域间协调访客ID服务的部署，则不需要设置宽限期。 要配置宽限期，请联系[Adobe客户关怀](https://helpx.adobe.com/cn/marketing-cloud/contact-support.html)。

## 跨域跟踪

某些旧版Analytics访客ID实施可能使用“友好的第三方Cookie”，其中两个域在像`data.example.com`这样的公共域上共享相同的访客Cookie。 由于友好的第三方Cookie仍然是第三方Cookie，因此大多数现代浏览器都会拒绝它们，从而导致Analytics依赖回退ID (`fid`)来识别访客。 迁移到ID服务后，所有域都可以在第一方上下文中设置`AMCV` Cookie，从而提高它们保留访客ID的可行性。

当访客ID服务尝试为跨域跟踪设置第三方Cookie([`demdex` Cookie](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies))时，它经常被大多数现代浏览器拒绝。 考虑使用[`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid)方法在您拥有的域之间传递Experience Cloud ID。

## 服务器端跟踪

您可以调用[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid)以获取Experience Cloud ID (`mid`)和[`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid)以获取旧版Analytics ID (`aid`)。 Adobe建议同时检查这两个变量，以保留访客识别逻辑。
