---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cb0eab15dac6d679e9f912010045e6be2e47df4a
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 45%

---

# 当前 Adobe Analytics 发行说明（2024 年 7 月）

**上次更新日期**：2024年7月17日

这些发行说明涵盖2024年7月17日至2024年8月的发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或增强功能 {#features}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| 针对链接跟踪的&#x200B;**Web SDK改进** | 最新版本的Web SDK中围绕链接跟踪提供了几项显着改进，这些改进直接有利于Activity Map。 这些新功能在Web SDK JavaScript库和Web SDK标记扩展中均可用。<ul><li>事件分组：当访客单击内部链接时，您可以选择将下一页面上的事件数据分组，而不是触发单独的链接跟踪事件调用。 这项改进减少了Web SDK违反合同限制使用的事件数。</li><li>筛选点击属性：替换`OnBeforeLinkClickSend`的新回调。 您可以使用此回调在发送链接相关数据到Adobe之前对其进行过滤或模糊处理。</li></ul><p>有关详细信息，请参阅Web SDK用户指南中的[clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection)。</p> | 开放式Beta于2024年7月10日开始 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修复

* 修复了阻止用户登录Analytics UI的问题(AN-352953)
* 修复了阻止用户登录Analytics移动设备应用程序的问题(AN-352463)
* 修复了阻止将项目下载为PDF的问题(AN-352680)
* 修复了未导入分类的问题(AN-352178)

### 其他 Analytics 修复

AN-352905； AN-352902； AN-352693； AN-352659； AN-352619；
AN-352577、AN-352575、AN-352572、AN-352571、AN-352549、AN-352501、AN-352499、AN-352478、AN-352466、AN-352437、AN-352378、AN-352355、AN-352341、AN-352318、AN-352297、AN-352272、AN-352267、AN-352263、AN-352088、AN-352019、AN-352018、AN-351978、AN-351908、AN-351809、AN-351750、AN-351689 -351624； AN-351564； AN-351524； AN-351507； AN-351416； AN-351414； AN-351405； AN-351299； AN-351283； AN-351231； AN-350710； AN-349912； AN-349786； AN-348300； AN-348061； AN-347865； AN-347676； AN-347478； AN-343611； AN-343114； AN-334124； AN-； AN-； AN-； AN-； AN-

## Adobe Analytics 管理员的重要注意事项 {#admin}

| 注意事项 | 添加或更新日期 | 描述 |
| ----------- | ---------- | ---------- |
| **保存的`cust_visids`** 13 个月有效期 | 2024 年 5 月 22 日 | 即将发布的 Analytics Hit 处理引擎&#x200B;**（预计于 2024 年 7 月发布）**&#x200B;将开始对保存的 `cust_visids` 强制执行 13 个月的有效期。如果报表包启用了“启用访客拼接”，则此设置可用于查找点击中没有 `cust_visid` 的 `visid_high/visid_low value` 的 `cust_visid`。目前，对 `visid_high/visid_low` 的 `cust_visid` 的映射没有有效期。在此版本中，如果自 `visid_high/visid_low` 点击 `cust_visid` 以来已经过去了 13 个月或更长时间，则映射会过期。 |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| Adobe Analytics API （版本1.4）的&#x200B;**EOL** | 2024年7月17日 | 在&#x200B;**2026年8月12日**，以下Analytics旧版API服务将停止使用并关闭，当前使用这些服务构建的集成将停止工作：<ul><li>Adobe Analytics API（版本1.4）</li><li>Adobe Analytics WSSE身份验证</li></ul><p>使用Adobe Analytics API（版本1.4）的集成必须迁移到[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而WSSE集成必须在[Adobe Developer Console](https://developer.adobe.com/console)中迁移到基于OAuth的身份验证协议。</p><p>有关常见问题的解答和进一步指导，请参阅[Adobe Analytics 1.4 API EOL常见问题解答](/help/admin/c-admin-api/c-admin-14-api-eol.md)。</p> |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[采用 OAuth 的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

有关 AppMeasurement 版本（版本 2.26.0）的最新更新，请参阅[适用于 JavaScript 的 AppMeasurement 发行说明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hans)。


## 相关资源

* [以前的 2024 年发行说明](/help/release-notes/2024.md)
* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hans)
* [流媒体收藏集附加组件发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版本更新
