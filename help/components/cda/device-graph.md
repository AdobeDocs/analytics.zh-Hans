---
title: 设备图
description: 了解使用设备图拼合数据的先决条件和限制。
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
feature: CDA
role: Admin
source-git-commit: cc0b8703d6b6488adf9a2ea41a51001538d1cbee
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 60%

---


# 设备图

{{available-existing-customers}}

Cross-Device Analytics可以使用专用图将数据拼合在一起。 专用图是特定于您的组织的经过哈希处理的设备ID的存储库。 CDA 会定期与设备图进行通信，以便将设备链接在一起。

## 特定于设备图的先决条件

如果您打算使用设备图方法来实施 Cross-Device Analytics，则需要满足以下条件。请与贵组织内的团队以及Adobe客户团队合作，确保您满足以下所有条件。

>[!WARNING]
>
>如果不满足所有先决条件，则可能会导致无法启用 Cross-Device Analytics，或者导致拼合数据时的结果不佳。
>

* [概述页面](overview.md)中列出了所有先决条件。
* 您的组织必须使用[Adobe Experience Platform Identity Service专用图](https://business.adobe.com/products/experience-platform/identity-service.html)。 另请参阅Identity Service用户指南中的[主页](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hans)。
* 您的实施必须使用最新版本的Experience CloudID服务(ECID)。 请参阅ID服务用户指南中的[主页](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。 在Adobe Experience Platform中使用[标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)的大多数实施可能都已部署ID服务。
* 当个人身份可以识别（例如，用户登录或打开电子邮件）时，您的实施必须调用 `setCustomerIDs` 函数（或等效的 SDK）。这项要求适用于所有平台，包括使用的移动设备应用程序。请参阅ID服务用户指南中的[`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=zh-Hans)。

## 特定于设备图的限制

* 不支持旧版 Analytics ID。仅拼合具有 Experience Cloud ID 的访客。
* 如果贵组织使用专用图，则拼合新设备最多需要 24 小时。
* 不支持第三方设备图。

## 后续步骤

贵组织在满足所有要求并了解相关限制后，便可以开始 [Cross-Device Analytics](setup.md)。
