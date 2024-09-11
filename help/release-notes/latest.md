---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a74d47cf99545305c9b7d99d934dfedafdd9233b
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 56%

---

# 当前 Adobe Analytics 发行说明（2024 年 9 月）


**上次更新日期**：2024年9月11日

这些发行说明涵盖2024年9月11日到10月初的发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
|--- | --- | --- | --- |
| **计算指标管理器和区段管理器的“用于”列中的其他信息** | 计算量度管理器和区段管理器中的“用于”列包含以下新报告区域：<ul><li>**Report Builder**：显示Report Builder中使用的计算指标或区段数。</li><li>**临时组件**：显示项目中使用的临时计算量度或临时区段数。 这些临时计算量度和区段（也称为“快速计算量度”和“快速区段”）只能在创建它们的项目中使用，因此它们会与“用于”列中的“项目”报表区域分开报告。</li></ul> |  | 2024年9月11日 |
| **Activity Mapv3扩展** | Activity Mapv3扩展现已可用。 如果已安装v2扩展，请先卸载该扩展，然后再安装v3扩展。 导航到&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Activity Map]**&#x200B;以获取扩展的最新版本。 |  | 2024年9月3日 |


## Adobe Analytics 中的修复

A4T： AN-355736
Activity Map：AN-353779
Analysis Workspace： AN-348485； AN-349693； AN-357247
Analytics移动设备应用程序：AN-352645
分类：AN-355636、AN-355651、AN-355753、AN-356005、AN-356439、AN-356540、AN-356577、AN-356622
Cross-Device Analytics： AN-355138
数据馈送：AN-356258；AN-357133
Data Warehouse：AN-339292；AN-353807
导出位置：AN-356912
隐私API： AN-352420
Report Builder：AN-352555；AN-354316
计划项目：AN-355971
分段：AN-352095；
Target报表：AN-355748

其他修复：AN-349698、AN-349880、AN-354860、AN-355355、AN-356289；

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **保存的`cust_visids`** 13 个月有效期限 | 2024 年 8 月 20 日 | Analytics Hit 处理引擎将于 **2024 年 8 月 20 日**&#x200B;发布，届时它会强制将保存的 `cust_visids` 的有效期限设为 13 个月。如果报表包启用了“启用访客拼接”，则此设置可用于查找点击中没有 `cust_visid` 的 `visid_high/visid_low value` 的 `cust_visid`。此前，对 `visid_high/visid_low` 的 `cust_visid` 的映射没有有效期限。在此版本中，如果自 `visid_high/visid_low` 点击 `cust_visid` 以来已经过去了 13 个月或更长时间，则映射会过期。 |
| **自动映射的其他实施详细信息XDM字段** | 2024年9月11日 | 使用Adobe Experience PlatformEdge Network将数据发送到Adobe Analytics时，XDM字段`xdm.implementationdetails.name`和`xdm.implementationdetails.environment`现在始终映射到上下文数据变量`c.a.x.implementationdetails.name`和`c.a.x.implementationdetails.environment`。 以前，某些场景会阻止填充这些值。 请调整任何相关的处理规则，以适应这些值的可用性。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **适用于 Adobe Analytics API（版本 1.4）的 EOL** | 2024 年 7 月 17日 | **2026 年 8 月 12 日**，以下 Analytics Legacy API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资产

* [以前的 2024 年发行说明](/help/release-notes/2024.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [流媒体收藏集附加组件发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
