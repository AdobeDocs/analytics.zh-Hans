---
description: 启用常规项目（帐单、日志等）、公司管理、工具、Web 服务访问、Report Builder 和 Data Connectors 集成的用户权限。
keywords: groups;permissions
subtopic: Users and groups
title: 自定义 Analytics 工具权限
topic: Admin tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

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

此页上的设置与页面上选定的报表包有关 [!UICONTROL Define User Groups] 。

| 元素 | 描述 |
|--- |--- |
| **常规** |  |
| [代码管理器](/help/admin/admin/code-manager-admin.md) | 允许下载适用于网络和移动平台的数据收集代码。 |
| 代码管理器 - Web 服务 | 允许非管理用户通过Web服务访问代码管理器。 |
| [日志](/help/admin/admin/logs.md) | 启用对日志文件的权限，这有助于您查看用户登录时间、用户使用情况、访问权限、报告套件和管理员更改。 |
| 日志 - Web 服务 | 允许非管理用户通过Web服务访问管理工具日志。 |
| [流量管理](/help/admin/c-traffic-management/traffic-management.md) | “流量管理”页可让您指定预期的流量变化。 |
| 权限管理 | 授予非管理员用户对“管理工具”中的“用户管理”页面的访问权限。 这些用户具有“读取”权限，但没有“写入”权限。 |
| 权限（写入）- Web 服务 | 授予非管理用户在Web服务中的“用户管理”下的读写权限设置。<br>此设置专门针对管理员 API 中指示的权限操作。 |
| 权限（读取）- Web 服务 | 允许非管理用户在Web服务中的“用户管理”下视图权限设置。<br>此设置专门针对管理员 API 中指示的权限操作。 |
| **公司管理** |  |
| [安全性](/help/admin/company/security-manager.md) | 授予通过“安全管理器”页面控制报表数据访问权限的权限。相关选项包括强密码、密码过期时间、IP 登录限制及电子邮件域限制。 |
| 支持信息 | 授予访问“公司设置”中的“支持信息”的权限。 |
| [Web 服务](/help/admin/company/web-services-admin.md) | 允许访问“管理工具”界面([!UICONTROL Company Settings] >)中的“Web服 [!UICONTROL Web Services]务”页。<br>Web 服务 API 提供了一种通过编程访问 Adobe Analytics 服务的方式，让您可以复制和扩展通过用户界面提供的功能。 |
| 单点登录（旧版） | 授予对“管理工具”中单一登录页面的访问权限。<br>**注意：**Adobe Experience Cloud 中的单点登录是通过 Experience Cloud 与各个解决方案之间的[帐户关联](https://marketing.adobe.com/resources/help/zh_CN/mcloud/organizations.html)实现的。 |
| [待定操作](/help/admin/company/pending-actions-admin.md) | Grants permission to manage pending actions in [!UICONTROL Company Settings]. |
| [品牌联合](/help/admin/company/co-branding-admin.md) | 授予对 Analytics 进行品牌联合的权限。 |
| [首选项](/help/admin/admin/preferences-manager.md) | 授予权限 [!UICONTROL Preference Manager]。 |
| [隐藏报表包](/help/admin/company/c-hide-report-suites.md) | 授予在 Adobe Analytics 用户界面中隐藏报表包的权限。 |
| **工具** | 这些设置允许访问Analytics工具（界面和应用程序）和高级功能，如细分和计算指标。 |
| [当前数据](https://marketing.adobe.com/resources/help/zh_CN/reference/data_latency.html) | 授予在报告中使用“当前数据”功能的权限。 |
| [Ad Hoc Analysis 授权用户](https://marketing.adobe.com/resources/help/zh_CN/dsc/) | 授予访问权限 [!UICONTROL Ad Hoc Analysis]。 |
| Web 服务访问 | 为非管理员启用Web服务访问。 生成Web服务凭据。 |
| [Report Builder](https://marketing.adobe.com/resources/help/zh_CN/arb/setup.html) | 授予此组成员对许可证的访 [!UICONTROL Report Builder] 问权限。 |
| [Analysis Workspace 访问权限](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/) | 授予用户访问 Analysis Workspace（[!DNL Adobe Analytics] 的推荐报表界面）的权限。 |
| [Reports and Analytics](https://marketing.adobe.com/resources/help/zh_CN/sc/user/) | 授予用户访问 Reports &amp; Analytics 的权限。 |
| [计算量度创建](https://marketing.adobe.com/resources/help/zh_CN/analytics/calcmetrics/) | 授予用户创建计算量度的权限。 |
| [区段创建](https://marketing.adobe.com/resources/help/zh_CN/analytics/segment/) | 授予用户创建区段的权限。 |
| **Data Connectors** |  |
| 集成（创建、更新或删除） | 授予创建、更新和删除 Data Connector 集成的权限。 |
