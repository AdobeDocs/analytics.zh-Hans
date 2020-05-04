---
description: 启用常规项目（帐单、日志等）、公司管理、工具、Web 服务访问、Report Builder 和 Data Connectors 集成的用户权限。
keywords: groups;permissions
subtopic: Users and groups
title: 自定义 Analytics 工具权限
topic: Admin tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: ad9a7729924636055e456d0fd7ab928be227034d

---


# 自定义 Analytics 工具权限

>[!IMPORTANT]
>
>用户和产品管理已移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html) 中。Adobe 会通知您何时迁移用户。After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** will be retired.

启用常规项目（帐单、日志等）、公司管理、工具、Web 服务访问、Report Builder 和 Data Connectors 集成的用户权限。

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL All Report Access]** > **[!UICONTROL Analytics Tools]** > **[!UICONTROL Customize]**

>[!NOTE] 2016 年秋季版本（10 月 20 日）对群组管理做出了一些更改。请参阅[管理方面的更改 - 2016 年秋季版](/help/admin/user-management2/c-user-management/permissions-changes.md)以了解更改摘要。

## 报表访问 - Analytics 工具

![](assets/report-access-analytics-tools.png)

Click **[!UICONTROL Customize]** to select items to which this group will have access.

## 字段描述

The settings on this page pertain to the report suites selected on the [!UICONTROL Define User Groups] page.

| 元素 | 描述 |
|--- |--- |
| **常规** |  |
| [代码管理器](/help/admin/admin/code-manager-admin.md) | 启用下载适用于 Web 和移动平台的数据收集代码的权限。 |
| 代码管理器 - Web 服务 | 允许非管理用户通过 Web 服务访问代码管理器。 |
| [日志](/help/admin/admin/logs.md) | 启用日志文件权限，日志文件有助于您了解用户登录的时间、用户使用情况、访问情况、报表包，以及管理员执行的更改。 |
| 日志 - Web 服务 | 允许非管理用户通过 Web 服务访问管理工具日志。 |
| [流量管理](/help/admin/c-traffic-management/traffic-management.md) | 使用“流量管理”页面可以指定预期流量的变更。 |
| 权限管理 | 授予非管理员用户访问管理工具中的“用户管理”页面的权限。这些用户具有“读取”权限，但没有“写入”权限。 |
| 权限（写入）- Web 服务 | 在 Web 服务中的“用户管理”下向非管理员用户授予读写权限设置。<br>此设置专门针对管理员 API 中指示的权限操作。 |
| 权限（读取）- Web 服务 | 允许非管理用户在 Web 服务中查看“用户管理”下的权限设置。<br>此设置专门针对管理员 API 中指示的权限操作。 |
| **公司管理** |  |
| [安全性](/help/admin/company/security-manager.md) | 授予通过“安全管理器”页面控制报表数据访问权限的权限。相关选项包括强密码、密码过期时间、IP 登录限制及电子邮件域限制。 |
| 支持信息 | 授予访问“公司设置”中的“支持信息”的权限。 |
| [Web 服务](/help/admin/company/web-services-admin.md) | 允许访问“管理工具”界面(>)中的“Web服[!UICONTROL Company Settings] 务” [!UICONTROL Web Services]页面。<br>Web 服务 API 提供了一种通过编程访问 Adobe Analytics 服务的方式，让您可以复制和扩展通过用户界面提供的功能。 |
| 单点登录（旧版） | 授予对管理工具中的单点登录页面的访问权限。<br>**注意：**Adobe Experience Cloud 中的单点登录是通过 Experience Cloud 与各个解决方案之间的[帐户关联](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/manage-users-and-products/organizations.html)实现的。 |
| [待定操作](/help/admin/company/pending-actions-admin.md) | Grants permission to manage pending actions in [!UICONTROL Company Settings]. |
| [品牌联合](/help/admin/company/co-branding-admin.md) | 授予对 Analytics 进行品牌联合的权限。 |
| [首选项](/help/admin/admin/preferences-manager.md) | 授予权限 [!UICONTROL Preference Manager]。 |
| [隐藏报表包](/help/admin/company/c-hide-report-suites.md) | 授予在 Adobe Analytics 用户界面中隐藏报表包的权限。 |
| **工具** | 以下设置授予对 Analytics 工具（界面和应用程序）及分段和计算量度等高级功能的访问权限。 |
| [当前数据](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html) | 授予在报表中使用“当前数据”功能的权限。 |
| [Ad Hoc Analysis 授权用户](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/ad-hoc-analysis/adhoc-home.html) | Grants permission to access [!UICONTROL Ad Hoc Analysis]. |
| Web 服务访问 | 为非管理员用户启用 Web 服务访问权限。生成 Web 服务凭据。 |
| [Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html) | Grants members of this group access to [!UICONTROL Report Builder] licenses. |
| [Analysis Workspace 访问权限](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html) | 授予用户访问 Analysis Workspace（[!DNL Adobe Analytics] 的推荐报表界面）的权限。 |
| [Reports and Analytics](https://docs.adobe.com/content/help/en/analytics/landing/an-key-concepts.html) | 授予用户访问 Reports &amp; Analytics 的权限。 |
| [计算量度创建](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/cm-overview.html) | 授予用户创建计算量度的权限。 |
| [区段创建](https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/seg-home.html) | 授予用户创建区段的权限。 |
| **Data Connectors** |  |
| 集成（创建、更新或删除） | 授予创建、更新和删除 Data Connector 集成的权限。 |
