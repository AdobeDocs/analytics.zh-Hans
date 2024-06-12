---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6349edc65b953ce7f41d5a5990c8afd6efa20d8d
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 57%

---

# 当前 Adobe Analytics 发行说明（2024 年 6 月）

**上次更新**：2024年6月12日

这些发行说明涵盖2024年6月12日至7月的发行期。 Adobe Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在自由格式表的下拉菜单中选择多个可用过滤器** | 当多个过滤器作为下拉菜单添加到自由格式表时，自由格式表的用户现在可以同时选择多个过滤器。 自由格式表将进行筛选，以包含任何选定的过滤器。 以前，用户在过滤器下拉菜单中一次只能选择一个过滤器。<p>（文档链接随后提供。） |  | 2024年6月19日 |
| **工作区项目的目录** | 现在有新的目录可用于项目。 目录提供了使用户能够快速跳转到项目中的面板和可视化图表的链接。 可以为单个项目或给定用户的所有项目启用目录。<p>（文档链接随后提供。） |  | 2024年6月19日 |
| **在自由格式表中为维度项目创建超链接** | 您可以为一个或多个维度项目创建超链接，以使它们可在Analysis Workspace的自由格式表中点击。 <p>您可以为具有URL值的维度项创建超链接，也可以为具有非URL值的维度项创建自定义URL。</p><p>您可以使用变量为多个维度项目创建动态自定义URL。 变量可以引用维度项的值，也可以引用划分维度。</p><p>（文档链接随后提供。）<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | 2024年6月19日 |
| **管理员设置控制用于导出和导入的帐户和位置** | 新 [位置管理器中的“管理员设置”选项卡](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) 管理员可控制用户是否可以创建和编辑帐户和位置。 这些设置适用于用户 [配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md) 和 [配置云导入和导出位置](/help/components/locations/configure-import-locations.md). <p>管理员还可以限制用户可以创建和使用的帐户类型（Google Cloud Platform、Azure RBAC、Amazon S3 等）。</p><p>以前，任何用户都可以创建、编辑和使用任何类型帐户的帐户和位置。</p> | 2024 年 6 月 12 日 | 2024 年 6 月 30 日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者以及系统管理员可以编辑和删除帐户和位置。<p>以前，帐户和位置只能由创建它们的用户使用。</p><p>当用户[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)以及[配置云导入或导出位置时，这些设置适用](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-locations)。 </p> | 2024 年 6 月 12 日 | 2024 年 6 月 30 日 |
| **Activity Map 减少了 Web SDK 服务器调用次数** | 目前，Activity Map 链接事件将计为其自己的事件，并且会产生额外费用。此增强功能获取一些链接事件并将它们打包到下一次点击中，类似于 AppMeasurement 处理事件的方式。 <p>（更新文档链接见下文）</p> | Beta 公测将于 2024 年 6 月 19 日开始 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了以下分类问题：AN-347682、AN-348396、AN-348625、AN-348668、AN-348926、AN-348936、AN-349040、AN-349191、AN-349195、AN-349443、AN-349697、AN-349758、AN-349862、AN-350051、AN-350054、AN-350208、AN-350497、AN-350525、AN-351067、AN-、AN-
* 修复了以下Data Warehouse问题：AN-346862、AN-349409、AN-349926、AN-350629、AN-350996
* 修复了以下数据馈送问题：AN-346727、AN-348282、AN-348334、AN-348725、AN-348726、AN-348823、AN-349081、AN-349207、AN-349307、AN-349539、AN-349710、AN-349729、AN-349742、AN-349878、AN-349943、AN-350527、AN-；
* 修复了以下数据源问题：AN-350038
* 修复了以下Analysis Workspace问题：AN-342953、AN-346346、AN-349590、AN-349717、AN-350057、AN-350697、AN-350904
* 修复了以下Report Builder问题：AN-348903；AN-350691
* 修复了以下 A4T 问题：AN-347690；AN-350853

### 其他 Analytics 修复

AN-346470、AN-346850、AN-347227、AN-348145、AN-348564、AN-349001、AN-349008、AN-349211、AN-349719、AN-350523；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **保存的`cust_visids`** 13 个月有效期 | 2024 年 5 月 22 日 | 即将发布的 Analytics Hit 处理引擎&#x200B;**（预计于 2024 年 7 月发布）**&#x200B;将开始对保存的 `cust_visids` 强制执行 13 个月的有效期。如果报表包启用了“启用访客拼接”，则此设置可用于查找点击中没有 `cust_visid` 的 `visid_high/visid_low value` 的 `cust_visid`。目前，对 `visid_high/visid_low` 的 `cust_visid` 的映射没有有效期。在此版本中，如果自 `visid_high/visid_low` 点击 `cust_visid` 以来已经过去了 13 个月或更长时间，则映射会过期。 |
| **ISO 区域更新** | 2024 年 5 月 10 日 | Adobe 将在 2024 年 6 月 7 日执行 2024 年 ISO 区域更新。预计在此次发布后将看到少量地理信息更新（区域）。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2024 年发行说明](/help/release-notes/2024.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
