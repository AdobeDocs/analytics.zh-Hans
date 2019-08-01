---
description: 'null'
seo-description: 'null'
seo-title: 受迁移影响的 API
title: 受迁移影响的 API
uuid: 9a5d43be-e146-476b-961e-49ea0 a30 b500
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# 受迁移影响的 API{#apis-affected-by-the-migration}

## 受迁移影响的 API {#topic-8d34296a67d74b1081c3f7e8f650f3ce}

Adobe 正在将所有 Analytics 登录公司从 [!DNL my.omniture.com] 是迁移出来，并通过 Adobe Experience Cloud 进行身份验证。公司开始此迁移后，将不再支持通过特定于 Analytics 的权限及 Analytics Admin API v1.3 与 v1.4 提供的 `GetLoginKey` 方法以编程方式创建和管理用户。此类操作将立即通过 [!DNL adobe.io] 在 Experience Cloud 中执行。

## 受影响的 API 方法 {#section-d19051ac26cc49aeb124f767c4760254}

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

## 可以执行的操作 {#section-8b0b89a862614f729ebdbe092ce99027}

如果贵公司当前正在使用这些方法，请查找自 2018 年 3 月 31 日开始发送的预迁移通知。此通知将在贵公司开始迁移到 Experience Cloud 身份验证之前至少 30 天发送，届时将不再支持使用这些方法。

如果贵公司不使用任何这些方法，那么除了确保您不会开始使用这些方法之外，便无需执行任何操作。

有关其他信息：

* [一般用户管理信息](https://helpx.adobe.com/enterprise/help/users.html)
* [通过 adobe.io 的用户管理 API](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [用户管理 API 论坛](https://forums.adobe.com/community/umapi/overview)
* [将 Analytics 用户访问和管理迁移到 Experience Cloud](https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/)

