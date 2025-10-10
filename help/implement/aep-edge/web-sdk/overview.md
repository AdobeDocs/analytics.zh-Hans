---
title: 使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics
description: 使用Web SDK将数据发送到Adobe Analytics。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 40%

---

# 使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) 向 Adobe Analytics 发送数据。 实现Web SDK有两种主要方法，每种方法都有两种实现类型：

| | **从AppMeasurement迁移** | **清理Web SDK实现** |
| --- | --- | --- |
| **使用标记** | [从Analytics扩展迁移到Web SDK扩展](analytics-extension-to-web-sdk.md) | [使用Web SDK扩展将数据发送到Adobe Analytics](web-sdk-tag-extension.md) |
| **使用JavaScript** | [从AppMeasurement迁移到Web SDK JavaScript库](appmeasurement-to-web-sdk.md) | [使用Web SDK JavaScript库将数据发送到Adobe Analytics](web-sdk-javascript-library.md) |

如果您的组织需要新的Web SDK实施，并且计划将来使用Customer Journey Analytics，则Adobe建议使用您自己的架构来实施干净的Web SDK。 请参阅Customer Journey Analytics用户指南中的[通过Adobe Experience Platform Web SDK摄取数据](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)。

## 其他资源

标记可高度定制。详细了解如何通过在实施中包含正确的数据来充分利用 Adobe Analytics。

- [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#?lang=zh-Hans)：了解界面的使用方式和可用的扩展。

- [Adobe Experience Platform Web SDK 文档](https://experienceleague.adobe.com/docs/web-sdk.html?lang=zh-Hans)
