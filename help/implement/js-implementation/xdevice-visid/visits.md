---
description: 每当发生服务器调用并且访问页码等于 1 时，Analytics 即会计为一次访问。
keywords: Analytics 实施
seo-description: 每当发生服务器调用并且访问页码等于 1 时，Analytics 即会计为一次访问。
seo-title: 访问
solution: Analytics
subtopic: 访客
title: 访问次数
topic: 开发人员和实施
uuid: 3035be-6f-6c-45df-a3 f2-5de6 d3 ed99 ce
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 访问次数

>[!IMPORTANT]
>
>不再建议跨设备识别访客的方法。Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

每当发生服务器调用并且访问页码等于 1 时，Analytics 即会计为一次访问。

If you look at the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 4 times: at hits 1, 9, 11, and 12. 与访客类似，该值会在初次关联后恢复正常，因为[!UICONTROL 访问页码]会由于有效[!UICONTROL 访客 ID] 发生更改而被重置为 1。
