---
title: 设备图
description: 了解使用设备图拼合数据的先决条件和限制。
translation-type: tm+mt
source-git-commit: 954927359420cfdb3d0e908758fc36464e15fee5
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 100%

---


# 设备图

跨设备分析提供了两种不同的方法来将数据拼合在一起。此方法使用 Adobe Experience Platform Identity Service 协作图或专用图将数据拼合在一起。CDA 会定期与设备图进行通信，以便将设备链接在一起。

## 协作图与专用图的区别

Adobe 在 ID 服务中提供了两种类型的设备图：

* **协作图**：任何客户都可以贡献和引用且经过哈希处理的设备 ID 的存储库。由于此类设备图是协作式的，因此，与专用图相比，它通常会匹配更多设备。
* **专用图**：只有您的组织可以引用且经过哈希处理的设备 ID 的存储库。

## 特定于设备图的先决条件

如果您打算使用设备图方法来实施跨设备分析，则需要满足以下条件。请与贵组织内的团队以及 Adobe 客户经理合作，确保满足以下所有条件。

>[!IMPORTANT]
>
>如果不满足所有先决条件，则可能会导致无法启用跨设备分析，或者导致拼合数据时的结果不佳。

* [概述页面](overview.md)中列出了所有先决条件。
* 贵组织必须使用 Adobe Experience Platform Identity Service 协作图或专用图。请参阅《Device Co-op 用户指南》中的[主页](https://docs.adobe.com/content/help/zh-Hans/device-co-op/using/home.html)。
* 您的实施必须使用最新版本的 Experience Cloud ID 服务。请参阅《Experience Cloud Identity Service 用户指南》中的[主页](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。大多数使用 Adobe Experience Platform Launch 的实施可能已经部署 ECID。
* 当个人身份可以识别（例如，用户登录或打开电子邮件）时，您的实施必须调用 `setCustomerIDs` 函数（或等效的 SDK）。这项要求适用于所有平台，包括使用的移动设备应用程序。请参阅《Experience Cloud Identity Service 用户指南》中的 [`setCustomerIDs`](https://docs.adobe.com/content/help/zh-Hans/id-service/using/id-service-api/methods/setcustomerids.html)。

## 特定于设备图的限制

* 不支持旧版 Analytics ID。仅拼合具有 Experience Cloud ID 的访客。
* 如果贵组织使用专用图，则拼合新设备最多需要 24 小时。
* 如果贵组织使用合作图，则拼合访问您网站的新设备可能最多需要 2 周。CDA 中针对最近两周数据的拼合级别，通常低于两周以前的日期范围。
* 不支持第三方设备图。

## 后续步骤

贵组织在满足所有要求并了解相关限制后，便可以开始[设置跨设备分析](setup.md)。

