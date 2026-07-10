---
title: 跨不同的实施类型跟踪
description: 使用不同的实施类型并在不同实施类型之间无缝跟踪访客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/FM6c33rpXxzy1huu8KE0VBkfe4FGIySczmVMrprFEUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 612
ht-degree: 47%

---

# 跨不同的实施类型跟踪

Adobe Analytics 实施的核心架构在所有实施类型中都是一致的。 此过程需要定义变量并将这些变量编译到一个图像请求中，然后将请求发送到 Adobe 数据收集服务器。 此概念意味着，您可以跨同一站点的不同页面在 AppMeasurement、Web SDK 以及它们在 Adobe Experience Platform 数据收集中各自的扩展之间无缝切换。

Adobe 建议通过在所有页面使用相同的实施类型来保持站点实施的一致性。 但是，如果您的网站的某些部分有不同的要求，则可以使用此页面来帮助确保在各页面之间持续跟踪访客。

如果您使用多种类型的实施（例如AppMeasurement和硬编码图像请求），请确保正确设置以下变量并彼此匹配。

>[!NOTE]
>
>所有实施类型必须使用相同的访客标识类型（旧版Analytics ID、访客ID服务或Experience Platform Identity Service）。 Adobe建议尽可能在所有实施中使用ECID。

| 变量 | Web SDK 标记扩展 | Web SDK(Alloy) | Analytics 扩展 | AppMeasurement | 硬编码图像请求 |
|---|---|---|---|---|---|
| 报告包 ID | [配置数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure)时添加 Adobe Analytics 作为服务 | [配置数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure)时添加 Adobe Analytics 作为服务 | [配置扩展](https://experienceleague.adobe.com/cn/docs/experience-platform/tags/extensions/client/analytics/overview)时的[!UICONTROL 库管理]部分下的[!UICONTROL 报告包] | [`s_gi`](../vars/functions/s-gi.md)中的字符串参数 | URL `pathname` 的一部分（`/b/ss/` 之后） |
| 访客ID服务 | 本机包含[Experience Platform Identity服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/home)；需要[`idMigrationEnabled`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/js/commands/configure/idmigrationenabled)才能读取访客ID服务Cookie | 本机包含[Experience Platform Identity服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/home)；需要[[!UICONTROL 将ECID从VisitorAPI迁移到Web SDK]](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/web-sdk/configure/identity)以读取访客ID服务Cookie | 使用实现[访客ID服务](https://experienceleague.adobe.com/cn/docs/id-service/using/home)的[“[!UICONTROL Experience Cloud ID服务]”标记扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/id-service/overview) | 实施[访客ID服务](https://experienceleague.adobe.com/cn/docs/id-service/using/home) (`VisitorAPI.js`) | 对访客ID服务[&#128279;](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/implementation/direct-integration)进行单独调用以获取所需的ID，并在查询字符串中包含`mid` |
| Edge域 | [配置扩展时[!UICONTROL Edge域]字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | [配置 Web SDK](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/commands/configure/overview) 时的 `edgeDomain` 属性 | 当[配置扩展](https://experienceleague.adobe.com/cn/docs/experience-platform/tags/extensions/client/analytics/overview)时，位于[!UICONTROL 常规]部分下的[!UICONTROL SSL跟踪服务器] | [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md)变量 | 图像请求 URL 的 `hostname` |

>[!NOTE]
>
>基于AppMeasurement的实施（包括Analytics标记扩展）与[Experience Platform Identity Service](https://experienceleague.adobe.com/cn/docs/id-service/using/home)不兼容。 您必须使用访客标识的最低通用分母形式才能跨实施类型进行同步，通常是[访客ID服务](https://experienceleague.adobe.com/cn/docs/id-service/using/home) (`VisitorAPI.js`)。

如果这些变量中的任何一个变量在每种实施类型中不一致，Adobe可能会将它们视为单独的访客。 如果未在您的网站上跨实施类型无缝跟踪访客，则最常见的原因是访客识别配置不正确。 确保每个实施类型在整个网站上正确获取相同的ECID （`mid` [查询字符串](/help/implement/validate/query-parameters.md)）。
