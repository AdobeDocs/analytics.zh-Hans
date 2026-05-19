---
description: 列出受用户迁移影响的 API
title: 受用户迁移影响的 API
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 31%

---

# 受用户迁移影响的 API{#apis-affected-by-the-migration}

Adobe正在将所有Analytics登录公司从[!DNL my.omniture.com]迁移到通过Adobe CX Enterprise进行身份验证。 公司开始此迁移后，将不再支持通过特定于 Analytics 的权限及 Analytics Admin API v1.3 与 v1.4 提供的 `GetLoginKey` 方法以编程方式创建和管理用户。 此类操作现在将通过`adobe.io`在CX Enterprise中启用。

## 受影响的 API 方法 {#methods}

一旦开始用户迁移，将不再支持管理员API v1.3和v1.4中的以下API方法：

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authinate
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## 您可以采取的操作 {#actions}

如果贵公司当前使用这些方法，请查找从2018年3月31日开始的迁移前通知。 通知将在贵公司开始迁移到CX企业身份验证之前至少30天发送，届时将停止支持这些方法。

如果您的公司未使用任何这些方法，则无需执行其他操作，只需确保您不开始使用这些方法。

有关其他信息：

* [常规用户管理信息](https://helpx.adobe.com/cn/enterprise/help/users.html)
* [用户管理API论坛](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [将Analytics用户访问和管理迁移到CX Enterprise](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
