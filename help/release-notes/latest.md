---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 88d60f38d5a87bacb755a49dc884700ac66039ce
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 76%

---

# 当前 Adobe Analytics 发行说明（2024 年 8 月）

**上次更新日期**：2024年8月14日

这些发行说明涵盖2024年8月14日至2024年9月的发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Web SDK 针对链接跟踪的改进** | 最新版本的 Web SDK 在链接跟踪方面做出了几项显著的改进，这可以直接使 Activity Map 受益。这些新功能在 Web SDK JavaScript 库和 Web SDK 标签扩展中均可用。<ul><li>事件分组：当访客点击内部链接时，您可以选择在下一页上对事件数据进行分组，而不是触发单独的事件调用进行链接跟踪。此项改进减少了 Web SDK 根据您的合同限制使用的事件数量。</li><li>过滤器点击属性：替换 `OnBeforeLinkClickSend` 的新回调。您可以使用此回调来过滤或混淆与链接相关的数据，然后再将其发送给 Adobe。</li></ul><p>有关更多信息，请参阅 Web SDK 用户指南中的 [clickCollection](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/commands/configure/clickcollection)。</p> | Beta 公测于 2024 年 7 月 10 日开始 | 2024年7月18日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了Workspace中显示多个未知值的问题(AN-353632)
* 修复了在Admin Console中添加新客户或新Analytics产品配置文件后未发送通知电子邮件的问题(AN-350930)

### 其他 Analytics 修复

AN-354361、AN-354248、AN-354211、AN-354324、AN-351532、AN-349808、AN-347831、AN-353777、AN-354092、AN-354064、AN-354202、AN-354006、AN-354097、AN-352548、AN-353819、AN-353818、AN-353628、AN-353747、AN-353527、AN-353490、AN-352647、AN-352656、AN-351274、AN-352135、AN-351519、AN-344906 AN-353697； AN-354499； AN-354402； AN-354062； AN-353905； AN-353932； AN-354142； AN-354194； AN-354182； AN-353758； AN-353039； AN-353612； AN-350799； AN-354414； AN-354636； AN-354249； AN-353637； AN-350949； AN-349402； AN-355103； AN-354174； AN-353823； AN-354819； AN-354215； AN-354219； AN-354040； AN-354763 AN-354597； AN-354478； AN-354528； AN-354335

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **保存的`cust_visids`** 13 个月有效期 | 2024 年 5 月 22 日 | 即将发布的 Analytics Hit 处理引擎&#x200B;**（预计于 2024 年 7 月发布）**&#x200B;将开始对保存的 `cust_visids` 强制执行 13 个月的有效期。如果报表包启用了“启用访客拼接”，则此设置可用于查找点击中没有 `cust_visid` 的 `visid_high/visid_low value` 的 `cust_visid`。目前，对 `visid_high/visid_low` 的 `cust_visid` 的映射没有有效期。在此版本中，如果自 `visid_high/visid_low` 点击 `cust_visid` 以来已经过去了 13 个月或更长时间，则映射会过期。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **适用于 Adobe Analytics API（版本 1.4）的 EOL** | 2024 年 7 月 17日 | **2026 年 8 月 12 日**，以下 Analytics Legacy API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) ，获取常见问题的解答和进一步的指导。</p> |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2024 年发行说明](/help/release-notes/2024.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [流媒体收藏集附加组件发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
