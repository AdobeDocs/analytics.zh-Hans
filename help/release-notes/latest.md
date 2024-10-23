---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2d42a824510fa03825a10da3837801ee662f687c
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 51%

---

# 当前Adobe Analytics发行说明（2024年10月23日版）


**上次更新时间**：2024年10月23日

这些发行说明涵盖2024年10月16日至2024年底的发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Analytics的新Report Builder** | 新的Report Builder应用程序为Adobe Analytics带来了重大更新，包括改进的性能、简化的用户界面、对Mac、Windows和Web浏览器上的Microsoft Excel的2.0 API支持和支持。 此应用程序可与旧版应用程序一起使用，但不能在同一文件上使用。 提供了升级功能，用于将旧版工作簿升级到新应用程序。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) |  | 2024 年 10 月 16 日 |
| 用于将Tags实施迁移到Web SDK标记的&#x200B;**JSON导出** | Analytics标记扩展的这项更新与迁移到Web SDK相关。 您可以将此更新用作Adobe Analytics扩展的工作流的一部分，以便通过Web SDK扩展重新创建扩展配置。 在Adobe Analytics标记扩展中，您可以以JSON格式查看eVar、prop和事件设置，可以导出该JSON进行编辑并包含在Web SDK扩展中。 |  | 2024 年 10 月 23 日 |

## Adobe Analytics 中的修复

Analysis Workspace： AN-356287； AN-358435； AN-359456； AN-359826； AN-360215
管理工具：AN-342485、AN-347931、AN-348704、AN-357723、AN-358453、AN-358717、AN-359548、AN-360136
分类：AN-359025、AN-359283、AN-359368、AN-359710、AN-359752、AN-359759、AN-359799、AN-359887、AN-360543、AN-360566、AN-360612、AN-360741、AN-360942、AN-360952
Cross-Device Analytics： AN-359210
客户属性：AN-357897
数据收集：AN-351131；AN-351309；AN-355678；AN-359856
数据馈送： AN-359699
数据修复API：AN-360256
数据源：AN-359290
Data Warehouse：AN-359820
超额警报：AN-358132


## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **非Campaign客户将失去对触发器的访问权限** | 2024 年 10 月 16 日 | 2025年1月30日，没有Adobe Campaign许可证的Adobe Analytics客户将失去配置和使用[触发器](https://experienceleague.adobe.com/en/docs/core-services/interface/services/triggers)功能的访问权限。 客户需要购买Campaign，或计划停止使用触发器，或研究其他提供触发器功能的Adobe工具。 |
| **自动映射的其他实现细节 XDM 字段** | 2024 年 9 月 11 日 | 使用 Adobe Experience Platform Edge Network 将数据发送到 Adobe Analytics 时，XDM 字段 `xdm.implementationdetails.name` 和 `xdm.implementationdetails.environment` 现在始终映射到上下文数据变量 `c.a.x.implementationdetails.name` 和 `c.a.x.implementationdetails.environment`。以前，某些场景会阻止这些值的填充。请调整任何相关的处理规则以适应这些值的可用性。 |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **适用于 Adobe Analytics API（版本 1.4）的 EOL** | 2024 年 7 月 17日 | 在&#x200B;**2026年8月12日**，以下Analytics旧版API服务将结束其生命周期并关闭，当前使用这些服务构建的集成将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-hans)。


## 相关资产

* [以前的 2024 年发行说明](/help/release-notes/2024.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hans)
* [流媒体收藏集附加组件发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
