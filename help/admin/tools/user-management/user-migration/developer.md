---
description: 列出受用户迁移影响的 API
title: 受用户迁移影响的 API
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 95%

---

# 受用户迁移影响的 API{#apis-affected-by-the-migration}

Adobe 正在将所有 Analytics 登录公司从 [!DNL my.omniture.com] 是迁移出来，并通过 Adobe Experience Cloud 进行身份验证。公司开始此迁移后，将不再支持通过特定于 Analytics 的权限及 Analytics Admin API v1.3 与 v1.4 提供的 `GetLoginKey` 方法以编程方式创建和管理用户。此类操作将立即通过 [!DNL adobe.io] 在 Experience Cloud 中执行。

## 受影响的 API 方法 {#methods}

开始用户迁移后，将不再支持 Admin API v1.3 和 v1.4 中的以下 API 方法：

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authenticate
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

## 可以执行的操作 {#actions}

如果贵公司当前正在使用这些方法，请查找自 2018 年 3 月 31 日开始发送的预迁移通知。此通知将在贵公司开始迁移到 Experience Cloud 身份验证之前至少 30 天发送，届时将不再支持使用这些方法。

如果贵公司不使用任何这些方法，那么除了确保您不会开始使用这些方法之外，便无需执行任何操作。

有关其他信息：

* [一般用户管理信息](https://helpx.adobe.com/cn/enterprise/help/users.html)
* [用户管理 API 论坛](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [将Analytics用户访问和管理迁移到Experience Cloud](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
