---
title: 适用于Adobe Analytics的访客ID服务迁移注意事项
description: 概述Adobe Analytics如何与访客ID服务进行交互。
exl-id: da1f9917-5254-41fb-9e2c-c94f66a22360
TQID: https://experienceleague.adobe.com/NnZ-Vv2M5cWkfekbVX1B-dFesdtxy50fMdTlwPYviYQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 678
ht-degree: 2%

---

# 适用于Adobe Analytics的访客ID服务迁移注意事项

如果您的组织计划使用现有的Analytics实施迁移到访客ID服务，则需要考虑一些重要主题。 这些注意事项允许您保持访客标识的完整性，并了解访客ID服务如何在现有Analytics实施的情况下运行。

>[!TIP]
>
>本页仅适用于现有AppMeasurement或Analytics扩展实施，并且是添加访客ID服务还是升级到Web SDK实施。 换言之，您的实施使用的是旧版Analytics ID (`aid`)，并且正在转为使用ECID (`mid`)。 所有Web SDK实施都使用[Experience Platform Identity服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/home)，该服务默认使用ECID (`mid`)。

## 访客ID服务如何与旧版Analytics访客Cookie进行交互

由于AppMeasurement具有其自身的旧版识别访客的方法，因此当组织部署访客ID服务时，某些访客可能现有Analytics Cookie。 下表概述了在不同情况下如何识别访客。

* **没有访客Cookie**：访客ID服务分配了ECID (`mid`)。
* **存在`s_vi` Cookie**：访客ID服务除了ECID (`mid`)之外，还将现有的旧版Analytics ID (`aid`)写入`AMCV` Cookie。 由于`aid`在[操作顺序](overview.md)中更高，在`AMCV` Cookie过期或被清除之前，旧版Analytics ID是访客标识符。 启用宽限期后，访客ID服务在其响应中同时包含`mid`和`aid`。
* **存在回退Cookie**：访客ID服务没有将回退Cookie (`fid`)写入`AMCV` Cookie。 相反，访客会收到ECID (`mid`)，就像他们是新访客一样。

## 访客ID服务宽限期

如果您有多个实施要将数据发送至同一报表包，并且您只能对某些实施实施实施访客ID服务，则Adobe建议配置一个宽限期。 例如，如果网站的支持部分由单独的标记解决方案管理，则您可能将访客ID服务部署在网站其他部分的支持部分之前。 如果没有宽限期，则查看支持部分的新访客会收到一个旧版Analytics访客ID，从而导致两个单独的访客被计数。 通过宽限期，访客ID服务会同时发出ECID (`mid`)和旧版Analytics访客ID (`aid`)，这样网站中没有访客ID服务的区域将保持一致的方式来识别访客。

如果您在网站的所有区域间协调访客ID服务的部署，则不需要设置宽限期。 要配置宽限期，请联系[Adobe客户关怀](https://helpx.adobe.com/cn/marketing-cloud/contact-support.html)。 宽限期最长可配置为180天，并且可以续订。 Adobe建议在将整个资产配置为使用访客ID服务后，停止宽限期。

## 跨域跟踪

某些旧版Analytics访客ID实施可能使用“友好的第三方Cookie”，其中两个域在像`data.example.com`这样的公共域上共享相同的访客Cookie。 由于友好的第三方Cookie仍然是第三方Cookie，因此许多现代浏览器会拒绝它们，从而导致Analytics依赖回退ID (`fid`)来识别访客。 迁移到访客ID服务后，所有域都可以在第一方上下文中设置`AMCV` Cookie，从而提高它们保留访客ID的可行性。

当访客ID服务尝试为跨域跟踪设置第三方Cookie([`demdex` Cookie](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/intro/cookies))时，它经常被现代浏览器拒绝。 考虑使用[`appendVisitorIDsTo`](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/id-service-api/methods/appendvisitorid)方法在您拥有的域之间传递访客的ECID (`mid`)。

## 服务器端跟踪

您可以调用[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/id-service-api/methods/getmcvid)以获取ECID (`mid`)和[`getAnalyticsVisitorID`](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid)以获取旧版Analytics ID (`aid`)。 Adobe建议同时检查这两个变量，以保留访客识别逻辑。
