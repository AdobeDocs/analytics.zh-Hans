---
description: 每当发生服务器调用并且访问页码等于 1 时，Analytics 即会计为一次访问。
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: 访问
topic: Developer and implementation
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 访问

>[!IMPORTANT]
>
>不再建议使用这种方法来识别跨设备访客。请参阅 [Adobe Experience cloud设备协作文档](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

每当发生服务器调用并且访问页码等于 1 时，Analytics 即会计为一次访问。

如果查看[前表](/help/implement/js-implementation/xdevice-visid/visit-example.md)，就会发现同一访客被计算了 4 次：即第 1、9、11 和 12 次点击。与访客类似，该值会在初次关联后恢复正常，因为[!UICONTROL 访问页码]会由于有效[!UICONTROL 访客 ID] 发生更改而被重置为 1。
