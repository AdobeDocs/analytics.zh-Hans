---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9fcf8871140e010d1c57c3af7004a45bd3a374a5
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 56%

---

# 当前的Adobe Analytics发行说明（2025年2月版）

**上次更新日期**：2024 年 2 月 21 日

这些发行说明涵盖2025年2月11日至3月中旬的发行时段。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **交易 ID 保留期限** | 交易ID保留期90天已延长至25个月。 `transactionID` 变量可唯一地标识交易，以便将点击绑定到通过数据源上传的数据。在[此处](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/transactionid)和[此处](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/transactionid)了解详情。 |  | 2025年2月20日 |
| **数据馈送API引用** | 数据馈送API的[引用](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs)现已可用。 |  | 2025 年 1 月 30 日 |
| **Livestream API — 客户端实施** | 使用Livestream客户端实施来使用Livestream数据。 [了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | 2025年2月18日 |
| **分类API更新** | 您现在可以从服务器中删除单个分类字段或密钥。 这提供了使用DELETE方法删除整个分类数据集的替代方法。 [了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/) |  | 2025年2月18日 |
| **更新Analytics上下文数据字段`a.locale`** | 计划的更新将在通过Experience Edge收集数据时更改Analytics上下文数据字段`a.locale`的设置方式。 使用Experience Edge将数据发送到Adobe Analytics时，Analytics字段会根据XDM字段的映射进行填充。 `c.a.locale`的映射引用了非标准XDM字段`xdm.environment.language`。 将更新此字段以引用正确的字段`xdm.environment._dc.language`。  为了向后兼容，映射将继续引用`xdm.environment.language`。 为保持连续性，如果同时设置了两个字段，则`xdm.environment.language`将优先。 您可以在[此处](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping)查看从XDM到标准Analytics字段的完整映射列表。 | | 2025年3月5日 |


## Adobe Analytics 中的修复

**Analysis Workspace**： AN-359974； AN-366212； AN-368460
**分类**： AN-367186； AN-367328； AN-368548
**组件迁移**： AN-364529； AN-366398； AN-367509；
**数据馈送**：AN-365685；AN-366745；AN-367256；AN-367349；AN-368363
**Data Warehouse**： AN-368178； AN-368331；
**移动设备应用程序**： AN-367137
**平台**： AN-351924； AN-365540； AN-365866； AN-366898； AN-367856； AN-367933
**Report Builder**： AN-366456； AN-366655；
**虚拟报表包**： AN-367411
**VISTA规则**： AN-365331

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **非 Campaign 客户将无法访问触发器** | 2023 年 10 月 16 日 | 2025年1月30日，没有Adobe Campaign许可证的Adobe Analytics客户无法访问配置和使用[触发器](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/services/triggers)的功能。 客户需要购买 Campaign，或者计划停止使用触发器，或者考虑提供触发器功能的其他 Adobe 工具。 |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 6 月 30 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **适用于 Adobe Analytics API（版本 1.4）的 EOL** | 2024 年 7 月 17日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-hans)。


## 相关资产

* [以前的 2024 年发行说明](/help/release-notes/2024.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
