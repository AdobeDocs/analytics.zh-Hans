---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ebe6716a3dde89d7212385c25044fb533d7737c2
workflow-type: ht
source-wordcount: '625'
ht-degree: 100%

---

# 当前的 Adobe Analytics 发行说明（2025 年 7 月版本）

**上次更新**：2025 年 7 月 16 日

这些发行说明涵盖 2025 年 7 月 7 日至 2025 年 8 月 15 日的发行期。Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **带有算法的 Livestream TNT 字段** | Livestream 正在进行更新，以确保该技术持续保持现代化和稳定性。作为此次更新的一部分，如果您的 TNT 字段中包含算法，我们将开始在 Livestream 输出中纳入该 TNT 字段。但此次仅涵盖先前已支持的元素：`campaignId`、`recipeId`、`trafficType`、`actionId` 和  `actionName`。Livestream 的整体 TNT 架构保持不变。 |   | 2025 年 7 月 7 日 |
| **更新了客户属性 UI 的导航** | 现在可以直接从 Adobe Experience Cloud 中的应用程序选择器访问客户属性用户界面。 | 2025 年 7 月 1 日 | 待定 |

## Adobe Analytics 中的修复

**Activity Map**：AN-360987
**Analysis Workspace**：AN-378094；AN-380979；AN-382908；AN-387652；
**分类**：AN-382412；AN-383157；AN-384616；AN-384803；AN-385933；AN-387320；AN-387351；AN-387832；AN-387833；AN-387839；AN-387915；
**数据收集**：AN-387661
**数据馈送**：AN-375172；AN-384369；AN-387859；AN-387952；AN-388155；
**平台**：AN-382813；AN-386627；AN-386815
**隐私**：AN-384390
**报表生成器**：AN-388035
**报告**：AN-380441
**计划报告**：AN-378280；AN-378331
**区段比较**：AN-368766


## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。所有用户都应开始将其旧工作簿升级到[新的 Report Builder](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/rb-overview)。新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。它具有[几乎相同的功能](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/convert-workbooks#unsupported)以及许多新的便捷功能和 UI 增强功能。要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。新的 Report Builder 仅通过 Microsoft Store 作为插件提供。许多组织要求在向用户提供加载项之前进行内部审批流程。请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **通过旧域或旧 SSO 访问** | 2025年 4 月 10 日 | Adobe 计划更新用户访问 Adobe Analytics 的方式，以增强安全性并简化您的登录体验。作为此项努力的一部分，通过旧域或旧 SSO（包括 `my.omniture.com`）进行的访问将于 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之后，旧版登录凭据和旧版 SSO 将不再起作用。所有用户都必需通过 `experience.adobe.com` 使用他们的 Adobe Experience Cloud ID 登录。如果您需要有关 Experience Cloud ID 方面的帮助，请联系您所在组织的 Adobe Analytics 管理员或 [Adobe 客户服务](https://helpx.adobe.com/cn/contact.html)。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。


## 相关资产

* [以前的 2025 年发行说明](/help/release-notes/2025.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
