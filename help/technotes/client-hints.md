---
title: 客户端提示
description: 了解客户端提示将如何逐渐取代 User-Agent 作为设备信息的来源。
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
source-git-commit: f80430a4537b17991a0c2cf104df47a053c3792d
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 91%

---

# 客户端提示概述和常见问题解答

客户端提示是单独的关于用户设备的信息。它们由 Chromium 浏览器提供，例如 Google Chrome 和 Microsoft Edge。对于这些浏览器，客户端提示将逐渐取代 User-Agent 作为设备信息的来源。Adobe Analytics 将更新其设备查找过程，以使它在 User-Agent 之外使用客户端提示确定设备信息。

Google 将 User-Agent 客户端提示分为两类：低熵提示和高熵提示。

* **低熵提示**&#x200B;包含更加通用的设备信息。Chromium 浏览器自动提供这些提示。

* **高熵**&#x200B;提示包含更加详细的信息。仅应请求提供这些提示。AppMeasurement 和 Web SDK 都可以配置为请求高熵提示。默认情况下，两个库都&#x200B;**不**&#x200B;请求高熵提示。

>[!NOTE]
>
>从 2023 年 1 月中旬开始，客户提示将纳入 Analytics 设备查找流程。AppMeasurement 和 Web SDK 目前都支持收集提示数据，但直到 1 月中旬才会用于设备查找。这是为了避免在关键的年终期间对报告的潜在干扰。如下所述，操作系统版本将从 10 月开始冻结，但由于逐步推出以及大多数用户代理将冻结到正确的操作系统版本，我们估计这将影响不到 3% 的 Chrome 访问者。

>[!NOTE]
>
>从 2022 年 10 月开始，Chromium 浏览器的新版本将开始“冻结”User-Agent 字符串中表示的操作系统版本。操作系统版本是高熵提示，因此要保证报表中操作系统版本的准确无误，必须配置收藏集库以使其收集这些高熵提示。User-Agent 的其他设备信息逐渐将被冻结，需要客户端提示以保持设备报表准确性。

>[!NOTE]
>
>AAM 需要收集高熵提示以保留完整功能。如果您正在使用[服务器端转发到 AAM 功能](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=zh-Hans)，则您可能希望启用高熵提示的收集。

## 常见问题解答

+++**在哪里可以了解到有关客户端提示的更多信息？**

此 [Google 博文](https://web.dev/user-agent-client-hints/)是一个很好的参考和起点。

+++

+++**如何启用客户端提示的收集？**

浏览器会自动提供低熵提示，这些提示经摄取后用于获取设备和浏览器信息。较新版本的 Web SDK（从 2.12.0 开始）和 AppMeasurement（从 2.23.0 开始）可以配置为通过各自的标记扩展或直接通过配置选项收集高熵提示。请参阅关于 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html#enabling-high-entropy-client-hints?lang=zh-Hans) 和 [AppMeaurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html?lang=zh-Hans) 的说明。

这两个库&#x200B;**在默认情况下禁用**&#x200B;高熵提示的收集。

+++

+++**我是否可以选择收集哪些高熵提示？**

目前还不可以。 您可以选择收集所有高熵提示，或者都不收集。

+++

+++**各种客户端提示值表示什么？**

下表对截至 2022 年 10 月的客户提示进行了说明。

| 提示 | 描述 | 高熵或低熵 | 示例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | 浏览器和重要版本 | 低 | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | 移动设备类型（true 或 false） | 低 | TRUE |
| Sec-CH-UA-Platform | 操作系统/平台 | 低 | &quot;Android&quot; |
| Sec-CH-UA-Arch | 网站架构 | 高 | &quot;arm&quot; |
| Sec-CH-UA-Bitness | 架构位 | 高 | &quot;64&quot; |
| Sec-CH-UA-Full-Version | 浏览器的完整版本 | 高 | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | 品牌及其版本的列表 | 高 | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | 设备型号 | 高 | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | 操作系统/平台版本 | 高 | &quot;10&quot; |

+++

+++**Analytics 中的设备报告是否会有任何变化？**

可用于报告的设备字段不会有任何变化。为这些字段捕获的数据可能会根据为客户端提示配置哪个字段以及如何为客户端提示配置收集而异。

+++

+++**从 User-Agent 获取哪些 Analytics 报表字段？**

这些字段直接从用户-代理派生，但用户-代理可用于帮助派生其他设备相关字段的值，具体取决于设备详细信息。

* [浏览器](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=zh-Hans)
* [浏览器类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=zh-Hans)
* [操作系统](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=zh-Hans)
* [操作系统类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=zh-Hans)
* [移动设备和移动设备类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=zh-Hans)

+++

+++**“冻结”User-Agent 的哪些部分以及何时冻结？**

请参阅 [Google 发布的时间表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)。此可能会有变化。

+++

+++**Analytics在哪些方面依赖于用户代理？**

报告中的设备信息是从用户代理派生的。 我们更新了流程，以便在可用时同时使用用户代理和客户端提示。

回退ID([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=en))是从用户代理和IP地址派生的。 此ID仅在无法设置Cookie时使用，因此不被广泛使用

+++

+++**从高熵提示中存储的值获取哪些 Analytics 报表字段？**

随着 Google“冻结”用户代理的更多部分，这将随着时间的推移而改变。第一个受到直接影响的字段是“操作系统”（其中包括操作系统版本）。根据 Google 发布的“冻结”用户-代理提示的时间表，操作系统版本将从 2022 年 10 月底的 Chromium 版本 107 开始冻结。届时，用户代理中的操作系统版本在某些情况下会不准确。

请参阅 [Google 发布的时间表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)以参阅冻结 User-Agent 其他部分的时机。

+++

+++**Adobe 将如何使用客户端提示获取设备信息？**

Adobe使用第三方Device Atlas ,Device Atlas将同时使用客户端提示和用户代理获取设备信息。

+++

+++**哪些浏览器会受到客户端提示的影响？**

客户端提示仅适用于 Chromium 浏览器，例如 Google Chrome 和 Microsoft Edge。来自其他浏览器或移动应用程序的数据没有变化。

+++

+++**是否在不安全的连接上支持客户端提示？**

否。只能通过安全的 HTTP 连接（如 HTTPS）收集客户端提示。

+++

+++**使用 API 提交时如何包含客户端提示数据？**

请参阅有关通过[批量数据插入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/) 包含这些数据的文档。

+++

+++**能否在通过 Adobe Source Connector 发送到 AEP 和 CJA 的数据中找到客户端提示？**

Adobe 计划在 2023 年上半年在通过 Adobe Source Connector 发送的数据中加入客户端提示。

+++

+++**在 XDM 中如何表示客户端提示？**

请参阅 Adobe Experience Platform 中的[架构文档](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)。

+++

+++**AAM 服务器端转发是否支持客户端提示？**

是的。客户端提示将包含在转发给 AAM 的数据中。请注意，AAM 需要收集高熵提示以保留完整功能。如果您正在使用[服务器端转发到 AAM 功能](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html)，则您可能希望启用高熵提示的收集。

+++
