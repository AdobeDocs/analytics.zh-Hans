---
title: 设备图
description: 使用设备图表了解拼接数据的先决条件和限制。
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 41%

---


# 设备图

跨设备分析提供两种不同的方法将数据拼接在一起。 该方法使用Adobe Experience Platform身份服务合作图或专用图将数据拼接在一起。 CDA定期与设备图进行通信，以将设备连接在一起。

## 合作图与私有图的区别

Adobe优惠两种类型的设备图形作为ID服务的一部分：

* **合作图**: 任何客户都可以提供并引用的散列设备ID的存储库。 由于此类设备图是协作的，因此与专用图相比，它通常匹配更多设备。
* **专用图**: 散列设备ID的存储库，仅供您的组织引用。

## 特定于设备图表的先决条件

如果您打算使用设备图表方法实施跨设备分析，则需要执行以下操作。 请与贵组织内的团队以及 Adobe 客户经理合作，确保满足以下所有条件。

>[!IMPORTANT]
>
> 如果不满足所有先决条件，则可能会导致无法启用跨设备分析，或者导致拼合数据时的结果不佳。

* 概述页面上列出的所 [有先决条件](overview.md)。
* 贵组织必须使用 Adobe Experience Platform Identity Service 协作图或专用图。请参阅《Device Co-op 用户指南》中的[主页](https://docs.adobe.com/content/help/zh-Hans/device-co-op/using/home.html)。
* 您的实施必须使用最新版的Experience CloudID服务。 请参阅《Experience Cloud Identity Service 用户指南》中的[主页](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。大多数使用 Adobe Experience Platform Launch 的实施可能已经部署 ECID。
* Your implementation must call the `setCustomerIDs` function (or SDK equivalent) whenever an individual can be identified, such as when a user logs in or opens an email. 这项要求适用于所有平台，包括使用的移动设备应用程序。请参阅《Experience Cloud Identity Service 用户指南》中的 [`setCustomerIDs`](https://docs.adobe.com/content/help/zh-Hans/id-service/using/id-service-api/methods/setcustomerids.html)。

## 设备图形的特定限制

* 不支持旧版 Analytics ID。仅拼合具有 Experience Cloud ID 的访客。
* 如果您的组织使用专用图，则新设备拼接最多需要24小时。
* 如果您的组织使用合作图，则访问您网站的新设备可能需要两周时间才能完成拼接。 CDA 中针对最近两周数据的拼合级别，通常低于两周以前的日期范围。
* 不支持第三方设备图。

## 后续步骤

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).

