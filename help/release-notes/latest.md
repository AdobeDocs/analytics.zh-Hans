---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d7beee25af3551426eb905f0e727545de068b2d9
workflow-type: ht
source-wordcount: '882'
ht-degree: 100%

---

# 当前 Adobe Analytics 发行说明（2025 年 1 月版本）

**上次更新日期**：2024 年 1 月 22 日

这些发行说明涵盖 2025 年 1 月 15 日至 2 月中旬的发行期。Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在新 Report Builder 中计划** | 计划不仅允许您安排新的 Report Builder 工作簿。此外，当您转换旧版工作簿时，它还允许您检索旧计划任务的元数据。这样，当您将旧版工作簿转换为新版工作簿并对其进行计划时，就可以将其以旧版工作簿相同的频率发送到相同的电子邮件。[了解详情](/help/analyze/report-builder/schedule-reportbuilder.md) |  | 2025 年 1 月 22 日 |
| **改进 Analysis Workspace 中的报告（也称为模板）** | 现在可以对报告（也称为模板）进行各种改进：<ul><li>现在称为[!UICONTROL 模板]（不再称为[!UICONTROL 报告]）。</li><li>改进了查看和查找模板的用户体验，包括在列视图或信息卡视图中查看模板的选项。</li><li>公司模板的新位置更加直观（位于 **[!UICONTROL Workspace]** > **[!UICONTROL 模板]**&#x200B;下）。</li><li>以前，创建项目时可以通过对话框访问公司模板。</li><li>提供更多预建模板。</li></ul>[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/templates/use-templates)。<p>管理员可以创建并保存模板，供登录公司的其他人使用。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/templates/create-templates) | 2025 年 1 月 15 日 | 2025 年 1 月 30 日 |
| **交易 ID 保留期限** | 交易 ID 的保留期限为 90 天，将于 2025 年 2 月延长至 25 个月。`transactionID` 变量可唯一地标识交易，以便将点击绑定到通过数据源上传的数据。（文档链接见下面） |  | 2025 年 2 月 11 日 |

## Adobe Analytics 中的修复

**A4T**: AN-355602; AN-365988
**Activity Map**: AN-365320
**Admin Console**: AN-363884
**管理工具**: AN-356747; AN-358776
**Advertising Analytics**: AN-355488
**Analysis Workspace**: AN-345318; AN-354801; AN-357052; AN-358975; AN-362886; AN-363831; AN-364124; AN-365257; AN-365319; AN-365462; AN-366194
**Analytics 1.4 API**: AN-358059
**分类**: AN-360049; AN-360424; AN-360745; AN-362208; AN-362345; AN-362560; AN-362576; AN-362633; AN-362653; AN-362762; AN-362815; AN-362881;  AN-362885; AN-362973; AN-363343; AN-363558; AN-363860; AN-364239; AN-364480; AN-364451; AN-364528; AN-364548; AN-364552; AN-364585; AN-364598; AN-364643; AN-364715; AN-364912; AN-364997; AN-365081; AN-365189; AN-365197; AN-365203; AN-365431; AN-365647; AN-365794; AN-366546
**组件迁移**: AN-362236; AN-365429
**贡献度分析**: AN-360146
**数据馈送**: AN-356997; AN-362470; AN-362498; AN-362775; AN-363323; AN-363413; AN-363569; AN-364063; AN-364142; AN-364294; AN-364298; AN-364325; AN-364367; AN-364594; AN-364995; AN-365127; AN-365272; AN-365519; AN-365760; AN-366152;
**数据修复 API**: AN-362773; AN-362874
**数据源**: AN-360745; AN-362202; AN-364566
**Data Warehouse**: AN-361447; AN-362616; AN-364524; AN-365108
**移动应用程序**: AN-362856; AN-365270
**超额警报**: AN-355594; AN-364547
**平台**: AN-358914; AN-360205; AN-362990; AN-364550; AN-365454; AN-365485
**Report Builder**: AN-363478; AN-364433; AN-365610
**报告活动管理器**: AN-362440
**分段**: AN-359921
**VISTA 规则**: AN-362927

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **非 Campaign 客户将无法访问触发器** | 2023 年 10 月 16 日 | 2025 年 1 月 30 日，没有 Adobe Campaign 许可证的 Adobe Analytics 客户将会失去配置和使用[触发器](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/services/triggers)的权限。客户需要购买 Campaign，或者计划停止使用触发器，或者考虑提供触发器功能的其他 Adobe 工具。 |

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
