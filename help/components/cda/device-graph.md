---
title: 设备图
description: 了解使用设备图拼合数据的先决条件和限制。
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: be913fb9bae7954864b180490364c275c7bf7f15
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 92%

---

# 设备图

跨设备分析可以使用专用图将数据拼合在一起。 专用图是特定于贵组织的经过哈希处理的设备ID的存储库。 CDA 会定期与设备图进行通信，以便将设备链接在一起。

## 特定于设备图的先决条件

如果您打算使用设备图方法来实施 Cross-Device Analytics，则需要满足以下条件。请与贵组织内的团队以及 Adobe 客户经理合作，确保满足以下所有条件。

>[!WARNING]
>
>如果不满足所有先决条件，则可能会导致无法启用 Cross-Device Analytics，或者导致拼合数据时的结果不佳。

* [概述页面](overview.md)中列出了所有先决条件。
* 贵组织必须使用 Adobe Experience Platform Identity Service 协作图或专用图。请参阅《Device Co-op 用户指南》中的[主页](https://experienceleague.adobe.com/docs/device-co-op/using/home.html?lang=zh-Hans)。
* 您的实施必须使用最新版本的 Experience Cloud ID 服务。请参阅《Experience Cloud Identity Service 用户指南》中的[主页](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。大多数使用 Adobe Experience Platform 中的标记的实施可能已经部署 ECID。
* 当个人身份可以识别（例如，用户登录或打开电子邮件）时，您的实施必须调用 `setCustomerIDs` 函数（或等效的 SDK）。这项要求适用于所有平台，包括使用的移动设备应用程序。请参阅《Experience Cloud Identity Service 用户指南》中的 [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=zh-Hans)。

## 特定于设备图的限制

* 不支持旧版 Analytics ID。仅拼合具有 Experience Cloud ID 的访客。
* 如果贵组织使用专用图，则拼合新设备最多需要 24 小时。
* 如果贵组织使用合作图，则拼合访问您网站的新设备可能最多需要 2 周。CDA 中针对最近两周数据的拼合级别，通常低于两周以前的日期范围。
* 不支持第三方设备图。

## 后续步骤

贵组织在满足所有要求并了解相关限制后，便可以开始 [Cross-Device Analytics](setup.md)。
