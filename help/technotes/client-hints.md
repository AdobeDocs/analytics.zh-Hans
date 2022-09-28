---
title: 客户端提示
description: 了解客户端提示将如何逐渐取代 User-Agent 作为设备信息的来源。
source-git-commit: f2f1e64a62796b58c24e6ff652db93b21f750669
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 100%

---


# 客户端提示概述和常见问题解答

客户端提示是单独的关于用户设备的信息。它们由 Chromium 浏览器提供，例如 Google Chrome 和 Microsoft Edge。对于这些浏览器，客户端提示将逐渐取代 User-Agent 作为设备信息的来源。Adobe Analytics 将更新其设备查找过程，以使它在 User-Agent 之外使用客户端提示确定设备信息。

Google 将 User-Agent 客户端提示分为两类：低熵提示和高熵提示。

* **低熵提示**&#x200B;包含更加通用的设备信息。Chromium 浏览器自动提供这些提示。

* **高熵**&#x200B;提示包含更加详细的信息。仅应请求提供这些提示。AppMeasurement 和 Web SDK 都[可以配置为](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md)请求高熵提示。默认情况下，这两个库都&#x200B;**不**&#x200B;请求高熵提示。

>[!NOTE]
>
>从 2022 年 10 月开始，Chromium 浏览器的新版本将开始“冻结”在 User-Agent 字符串中表示的操作系统版本。当用户升级其设备时，User-Agent 中的操作系统不变。因此，在 User-Agent 中表示的操作版本信息将逐渐降低准确性。操作系统版本是高熵提示，因此要保证报表中操作系统版本的准确无误，必须配置收藏集库以使其收集这些高熵提示。User-Agent 的其他设备信息逐渐将被冻结，需要客户端提示以保持设备报表准确性。

## 常见问题解答

+++**在哪里可以了解到有关客户端提示的更多信息？**

此 [Google 博文](https://web.dev/user-agent-client-hints/)是一个很好的参考和起点。

+++

+++**如何启用客户端提示的收集？**

在 Adobe 获取设备和浏览器信息的过程中，浏览器自动提供低熵提示。可将较高版本的 AppMeasurement（从 2.23.0 起）和 Web SDK（从 2.12.0 起）配置为收集高熵提示。对于这两个库，都在&#x200B;**默认情况下禁用**&#x200B;高熵提示的收集。

+++

+++**如何捕获高熵提示？**

可用 Web SDK 和 AppMeasurement 库通过其各自的标记扩展或直接用 collectHighEntropyUserAgentHints 标志配置高熵提示。

+++

+++**我是否可以选择收集哪些高熵提示？**

目前还不可以。 您可以选择收集所有高熵提示，或者都不收集。

+++

+++**Analytics 中的设备报告是否会有任何变化？**

可用于报告的设备字段不会有任何变化。为这些字段捕获的数据可能会根据为客户端提示配置哪个字段以及如何为客户端提示配置收集而异。

+++

+++**从 User-Agent 获取哪些 Analytics 报表字段？**

* [浏览器](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=zh-Hans)
* [浏览器类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=zh-Hans)
* [操作系统](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=zh-Hans)
* [操作系统类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=zh-Hans)
* [移动设备和移动设备类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=zh-Hans)
* [数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans)

+++

+++**从高熵提示中存储的值获取哪些 Analytics 报表字段？**

截至 2022 年 9 月，Google 关于“冻结”User-Agent 提示发布的时间表指示将从 2022 年 10 月开始停止更新操作系统版本。当用户升级其操作系统时，User-Agent 中的操作系统版本不更新。没有了高熵提示，（包括在 Analytics“操作系统”维度中的）操作系统版本的准确性将逐渐降低。

请参阅 [Google 发布的时间表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)以参阅冻结 User-Agent 其他部分的时机。

+++

+++**Adobe 将如何使用客户端提示获取设备信息？**

Adobe 使用第三方 Device Atlas，后者同时使用客户端提示和 User-Agent 获取设备信息。

+++

+++**哪些浏览器会受到客户端提示的影响？**

客户端提示仅适用于 Chromium 浏览器，例如 Google Chrome 和 Microsoft Edge。来自其他浏览器或移动应用程序的数据没有变化。

+++

+++**是否在不安全的连接上支持客户端提示？

否。只能通过安全的 HTTP 连接（如 HTTPS）收集客户端提示。

+++

+++**能否在通过 Adobe Source Connector 发送到 AEP 和 CJA 的数据中找到客户端提示？**

Adobe 计划在 2023 年上半年在通过 Adobe Source Connector 发送的数据中加入客户端提示。

+++

+++**在 XDM 中如何表示客户端提示？**

请参阅 Adobe Experience Platform 中的[架构文档](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)。

+++

+++**提示字段有哪些？哪些字段会影响设备报告？**

下表对截至 2022 年 9 月的客户提示进行了说明。

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



+++**“冻结”User-Agent 的哪些部分以及何时冻结？**

请参阅 [Google 发布的时间表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)。此可能会有变化。

+++
