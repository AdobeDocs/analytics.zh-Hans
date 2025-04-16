---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e2e387f20d5e5732ec1d7eb67a0c81df95e07a55
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 51%

---

# 当前Adobe Analytics发行说明（2025年4月版）

**上次更新时间**：2025年4月16日

这些发行说明涵盖 2025 年 3 月 26 日至 5 月的发行期。Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics清单** | Analytics清单提供了Adobe Analytics环境的全面概述，包括项目和组件数量、报表包数量、用户数量等。 通过自动化清点过程，您可以快速了解从Adobe Analytics切换到Customer Journey Analytics所需的工作。 这将使转换更容易、更快。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory) |  | 2025 年 3 月 26 日 |
| **Data Warehouse 专用维度** | 根据客户反馈，我们决定重新评估。 我们不会像之前宣布的那样发布仅限Data Warehouse的自动维度功能。 | | 待定 |

## Adobe Analytics 中的修复

**A4T**： AN-370625； AN-371279； AN-371351
**管理工具**： AN-365072； AN-371303
**Analysis Workspace**： AN-363831； AN-369554
**分类**： AN-370519、AN-370727、AN-370827、AN-370941、AN-370995、AN-371377、AN-371597、AN-371868、AN-371869、AN-372510、AN-372650、AN-373164、AN-373300、AN-373308、AN-373592
**数据收集**： AN-371877
**数据馈送**： AN-368676、AN-370225、AN-370514、AN-370521、AN-370687、AN-370761、AN-370911、AN-371047、AN-371542、AN-371627、AN-371746、AN-372708、AN-373068、AN-373179
**Data Warehouse**： AN-366649； AN-369817； AN-370705； AN-371127； AN-371995； AN-372596； AN-372940
**营销渠道**： AN-372308
**移动设备应用程序**： AN-370287； AN-371335； AN-371374
**平台**： AN-369510； AN-370435； AN-372150
**Report Builder**： AN-369830； AN-371395； AN-372983

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 不适用 |  |  |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **通过旧域或通过旧版SSO访问** | 2025年4月10日 | Adobe计划更新用户访问Adobe Analytics的方式，以增强安全性并简化您的登录体验。 作为此工作的一部分，通过旧域或通过旧版SSO（包括`my.omniture.com`）进行的访问将于&#x200B;**2026年1月2日**&#x200B;永久停止。 在此日期之后，旧版登录凭据和旧版SSO将不再有效。 所有用户都需要使用其Adobe Experience Cloud ID通过`experience.adobe.com`登录。 如果您需要有关Experience Cloud ID的帮助，请联系贵组织的Adobe Analytics管理员或[Adobe客户关怀](https://helpx.adobe.com/contact.html)。 |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 6 月 30 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **适用于 Adobe Analytics API（版本 1.4）的 EOL** | 2024 年 7 月 17日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关AppMeasurement版本的最新更新，请参阅[AppMeasurement发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
