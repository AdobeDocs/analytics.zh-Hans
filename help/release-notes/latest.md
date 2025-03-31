---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 53175bbf54dd452502e1502b272ebb86c8b133ef
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 64%

---

# 当前的 Adobe Analytics 发行说明（2025 年 3 月版本）

**上次更新时间**：2025年3月31日

这些发行说明涵盖 2025 年 3 月 5 日至 5 月的发行期。Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新 Analytics 上下文数据字段`a.locale`** | 此项更新改变了通过 Experience Edge 收集数据时 Analytics 上下文数据字段 `a.locale` 的设置方式。使用 Experience Edge 将数据发送到 Adobe Analytics 时，将根据 XDM 字段的映射填充 Analytics 字段。 `c.a.locale` 的映射参考了一个非标准 XDM 字段，`xdm.environment.language`。此字段将被更新以参考正确的字段，`xdm.environment._dc.language`。<p>该映射将继续参考 `xdm.environment.language` 以确保向后兼容。为了保持连续性，如果设置了两个字段，则 `xdm.environment.language` 优先。您可以[在此处](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/xdm-var-mapping)查看从 XDM 到标准 Analytics 字段的映射的完整列表。 | | 2025 年 3 月 5 日 |
| **Customer Journey Analytics 升级指南** | 让您生成从 Adobe Analytics 升级到 Customer Journey Analytics 的分步指南。本指南是根据您的组织量身定制的，并考虑了您当前的 Adobe Analytics 环境、您对 Customer Journey Analytics 的预期用途以及您的组织想要做出的任何节省时间的权衡。<p>要开始生成自定义指南，请登录 [!DNL Customer Journey Analytics]，然后在 **[!UICONTROL Workspace]** 选项卡上选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。<p>[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 2025 年 3 月 11 日 |
| **Data Warehouse 专用维度** | 从2025年5月开始，Adobe将开始将某些维度（自定义变量，如eVar和prop）设置为“仅限Data Warehouse”。 这适用于具有以下特征的尺寸：<ul><li> 在几个月的时间内，变量会在每月的前几天内达到低流量限制。</li><li>超过90%传入的值在一个月内只会看到一次。</li></ul>例如，包含时间戳、UUID或其他数据的维度，这些维度的基数非常高，并且在整个月内几乎每次点击（或访问或访客）都会传入唯一的新值。这些维度通常很快就会超过低流量限制，并且在Analysis Workspace中可报告的值只有很小的一部分。 这使得使用这些维度的报表难以理解，因为它们不会显示有用或准确的信息。 这些维度不遵循低流量功能的目的或从中受益，低流量功能旨在提供一种方法，用于在维度本月超过低流量限制后报告变为“受欢迎”的值。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic.)<p>标记为“仅限Data Warehouse”的维度将不可用于Analysis Workspace中的报表。 但是，它们仍可以通过Data Warehouse进行报告，因为低流量限制在此处不适用。<p>这并不意味着每个达到低流量限制的维度都是标记为“仅限Data Warehouse”的候选维度。 大多数达到低流量限制的维度实际上达到了低流量功能的目的：<ul><li>传入的大多数值都不是唯一的。</li><li>当月达到低流量限制后，公用值会继续输入。</li><li>新的“popular”值仍然可能出现。</li></ul>只有传入的几乎所有值都是新值且唯一的维度才会标记为“仅限Data Warehouse”。 鉴于在这些情况下所收集数据的唯一性，增加低流量限制不是解决办法。 | | 2025 年 5 月 |


## Adobe Analytics 中的修复

**Activity Map**：AN-361038
**管理工具**：AN-362178；AN-369483
**分析 API 1.4**：AN-369615
**Analysis Workspace**：AN-353491；AN-363403；AN-367230；AN-367313；AN-368582；AN-369821；AN-370227；
**分类**：AN-369848；AN-370196；AN-370226；AN-370437
**数据馈送**：AN-366162；AN-368906；AN-369066；AN-369087；AN-369225；AN-369798
**数据治理**：AN-365157
**数据源**：AN-367550
**平台**：AN-363931
**Report Builder**：AN-367460；AN-368975

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| 不适用 |  |  |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 6 月 30 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **适用于 Adobe Analytics API（版本 1.4）的 EOL** | 2024 年 7 月 17日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关AppMeasurement版本的最新更新，请参阅[AppMeasurement发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
