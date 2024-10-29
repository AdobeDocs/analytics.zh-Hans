---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 04a6b5ac6e60f1cc2d1579306581a1025eb83230
workflow-type: ht
source-wordcount: '767'
ht-degree: 100%

---

# 当前的 Adobe Analytics 发行说明（2024 年 10 月 23 日版本）

**上次更新日期**：2024 年 10 月 23 日

这些发行说明涵盖 2024 年 10 月 16 日至 2024 年末的发行期。Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Analytics 的新的 Report Builder** | 新的 Report Builder 应用程序为 Adobe Analytics 带来了一项重大更新，其中包括改进的性能、简化的用户界面、2.0 API 支持以及对 Mac、Windows 和 Web 浏览器上的 Microsoft Excel 的支持。此应用程序可以与旧版应用程序一起使用，但不能用于同一个文件。提供升级功能以将旧版工作簿升级到新的应用程序。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/report-buider-overview) |  | 2024 年 10 月 16 日 |
| **JSON 导出用于将标记实施迁移到 Web SDK 标记** | 此次对 Analytics 标记扩展的更新与迁移到 Web SDK 相关。您可以将此 Adobe Analytics 扩展更新用作工作流程的一部分，以使用 Web SDK 扩展重新创建扩展配置。在 Adobe Analytics 标记扩展中，您可以以 JSON 查看 eVars、props 和事件设置，并可将其导出进行编辑，还可以将其包含在 Web SDK 扩展中。 |  | 2024 年 10 月 31 日 |
| **有关 Analysis Workspace 性能中的请求因素的新信息** | 在 Analysis Workspace 中分析性能时，现在可以使用新的“请求因素”部分。要深入了解请求的处理方式以及影响处理时间的各种因素，请参阅[优化 Analysis Workspace 性能](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance)中的“请求因素”部分。 |  | 2024 年 10 月 1 日 |

## Adobe Analytics 中的修复

Analysis Workspace：AN-356287；AN-358435；AN-359456；AN-359826；AN-360215
管理工具：AN-342485；AN-347931；AN-348704；AN-357723；AN-358453；AN-358717；AN-359548；AN-360136
分类：AN-359025；AN-359283；AN-359368；AN-359710；AN-359752；AN-359759；AN-359799；AN-359887；AN-360543；AN-360566；AN-360612；AN-360741；AN-360942；AN-360952
跨设备分析：AN-359210
客户属性：AN-357897
数据收集：AN-351131；AN-351309；AN-355678；AN-359856
数据馈送：AN-359699
数据修复 API：AN-360256
数据源：AN-359290
Data Warehouse：AN-359820
超额警报：AN-358132

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **非 Campaign 客户将无法访问触发器** | 2023 年 10 月 16 日 | 2025 年 1 月 30 日，没有 Adobe Campaign 许可证的 Adobe Analytics 客户将会失去配置和使用触发器的权限。客户需要购买 Campaign，或者计划停止使用触发器，或者考虑提供触发器功能的其他 Adobe 工具。 |
| **自动映射的其他实现细节 XDM 字段** | 2024 年 9 月 11 日 | 使用 Adobe Experience Platform Edge Network 将数据发送到 Adobe Analytics 时，XDM 字段 `xdm.implementationdetails.name` 和 `xdm.implementationdetails.environment` 现在始终映射到上下文数据变量 `c.a.x.implementationdetails.name` 和 `c.a.x.implementationdetails.environment`。以前，某些场景会阻止这些值的填充。请调整任何相关的处理规则以适应这些值的可用性。 |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **适用于 Adobe Analytics API（版本 1.4）的 EOL** | 2024 年 7 月 17日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-hans)。


## 相关资产

* [以前的 2024 年发行说明](/help/release-notes/2024.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hans)
* [流媒体收藏集附加组件发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
