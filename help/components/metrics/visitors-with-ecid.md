---
title: 具有 Experience Cloud ID 的访客
description: 使用Adobe Experience Cloud ID服务的唯一访客数。
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 19%

---


# 具有 Experience Cloud ID 的访客

“具有Experience Cloud ID的访客”量度显示Adobe使用Experience Cloud ID服务识别的唯 [一访客数](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。 此维度有助于与“唯一 [访客](unique-visitors.md) ”量度进行比较，以确保站点的大多数访客都使用ID服务。 如果大部分访客不使用ID服务Cookie，则它可以指示您的实施中存在问题。

>[!NOTE] 如果您使用Adobe目标或Adobe受众管理器等多项Experience Cloud服务，则此指标对于调试尤为重要。 在Experience Cloud产品中共享的细分不包括没有Experience Cloud ID的访客。

## 如何计算此度量

此度量基于唯一 [访客](unique-visitors.md) ，但仅包括使用查询字符串(基于 `mid`[`s_ecid`](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/ec-cookies/cookies-analytics.html) cookie)标识的个人。

## 调试Experience Cloud ID设置

“具有Experience Cloud ID的访客”量度可用于诊断Experience Cloud集成故障，或识别未部署ID服务的站点区域。

将“具有Experience Cloud ID的访客”与“唯一访客”并排拖动，以进行比较：

![独特访客比较](assets/metric-mcvid1.png)

在此示例中，请注意，每个页面的“唯一访客”数与“具有Experience Cloud ID的访客”相同。 但是，独特访客的总数大于具有 Experience Cloud ID 的访客总数。您可以创建计 [算度量](../c-calcmetrics/cm-overview.md) ，以找出哪些页面未设置ID服务。 您可以使用以下定义：

![计算度量定义](assets/metric-mcvid2.png)

通过将计算量度添加到报表，您可以对页面报表进行排序，以便显现无 MCID 的访客数量最高的页面：

![无ID服务的页面](assets/metric-mcvid3.png)

请注意，“产品快速视图”维度值未通过Identity Service正确实现。 您可以与组织内的适当团队合作，以尽快更新这些页面。 您可以使用任何类型的维(如浏览器类型、 [站点区](../dimensions/browser-type.md)[域或任何eVar](../dimensions/site-section.md))构建类 [似报表](../dimensions/evar.md)。
