---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2b13f649d286e9eb707f2dd22c068b9742c51c70
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 56%

---

# 当前Adobe Analytics发行说明（2025年3月版）

**上次更新时间**：2025年3月12日

这些发行说明涵盖2025年3月5日至5月的发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新 Analytics 上下文数据字段`a.locale`** | 此更新更改了通过Experience Edge收集数据时Analytics上下文数据字段`a.locale`的设置方式。 使用 Experience Edge 将数据发送到 Adobe Analytics 时，将根据 XDM 字段的映射填充 Analytics 字段。 `c.a.locale` 的映射参考了一个非标准 XDM 字段，`xdm.environment.language`。此字段将被更新以参考正确的字段，`xdm.environment._dc.language`。<p>该映射将继续参考 `xdm.environment.language` 以确保向后兼容。为保持连续性，如果同时设置了两个字段，则`xdm.environment.language`优先。 您可以[在此处](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/xdm-var-mapping)查看从 XDM 到标准 Analytics 字段的映射的完整列表。 | | 2025 年 3 月 5 日 |
| **Customer Journey Analytics升级指南** | 允许您生成从Adobe Analytics升级到Customer Journey Analytics的分步指南。 本指南为您的组织量身定制，它考虑了您当前的Adobe Analytics环境、您对Customer Journey Analytics的预期用途，以及您的组织希望做出的任何节省时间的权衡。<p>要开始生成自定义指南，请登录到[!DNL Customer Journey Analytics]，然后在&#x200B;**[!UICONTROL Customer Journey Analytics]**&#x200B;选项卡上选择&#x200B;**[!UICONTROL 升级到Workspace]**。<p>[了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 2025年3月11日 |
| **仅限Data Warehouse的维度** | 从2025年5月开始，Adobe将开始设置维度（自定义变量，如eVar和prop），这些维度的“仅Data Warehouse”基数会非常高。 高基数变量具有许多不同的值；示例包括时间戳或UUID。 这些维度将不再可用于Analysis Workspace中的报表。<p>进行此更改的候选维度将在本月早些时候超过低流量限制。 对于这些类型的维度，Analysis Workspace中基于该维度的报表没有用处，因为可报告数据只表示收集到的初始值的一小部分。<p>由于Data Warehouse不施加低流量限制，因此您仍然可以根据这些类型的维度构建有用的报表或区段。 | | 2025 年 5 月 |


## Adobe Analytics 中的修复

**Activity Map**： AN-361038
**管理工具**： AN-362178； AN-369483
**Analytics API 1.4**： AN-369615
**Analysis Workspace**： AN-353491；AN-363403；AN-367230；AN-367313；AN-368582；AN-369821；AN-370227；
**分类**： AN-369848； AN-370196； AN-370226； AN-370437
**数据馈送**： AN-366162； AN-368906； AN-369066； AN-369087； AN-369225； AN-369798
**数据管理**： AN-365157
**数据源**： AN-367550
**平台**： AN-363931
**Report Builder**： AN-367460； AN-368975

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

有关 AppMeasurement 版本（版本 2.27.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-hans)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
