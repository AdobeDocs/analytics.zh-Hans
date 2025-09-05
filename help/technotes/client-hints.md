---
title: 客户端提示
description: 了解客户端提示将如何逐渐取代 User-Agent 作为设备信息的来源。
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
feature: Data Configuration and Collection
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 84%

---

# 客户端提示概述和常见问题解答

客户端提示是单独的关于用户设备的信息。它们由 Chromium 浏览器提供，例如 Google Chrome 和 Microsoft Edge。对于这些浏览器，客户端提示将逐渐取代 User-Agent 作为设备信息的来源。Adobe Analytics 将更新其设备查找过程，以使它在 User-Agent 之外使用客户端提示确定设备信息。

## 低熵和高熵客户端提示

Google 将 User-Agent 客户端提示分为两类：低熵提示和高熵提示。

* **低熵提示**&#x200B;包含更加通用的设备信息。Chromium 浏览器自动提供这些提示。

* **高熵**&#x200B;提示包含更加详细的信息。仅应请求提供这些提示。AppMeasurement 和 Web SDK 都可以配置为请求高熵提示。默认情况下，两个库都&#x200B;**不**&#x200B;请求高熵提示。

从 2022 年 10 月开始，Chromium 浏览器的新版本已开始“冻结”在 User-Agent 字符串中表示的操作系统版本。操作系统版本是高熵提示，因此要保证报告中操作系统版本的准确无误，必须配置收藏集库以使其收集这些高熵提示。User-Agent 的其他设备信息逐渐将被冻结，需要客户端提示以保持设备报告准确性。

从2023年2月27日开始，客户端提示将纳入Analytics设备查找流程，并将于2023年3月2日结束。 AppMeasurement 和 Web SDK 目前都支持收集提示数据，但直到 2 月中旬才会用于设备查找。如下所述，操作系统版本已从 10 月开始冻结，但由于逐步推出以及许多用户代理已提高冻结的操作系统版本（有关更多信息，请参见[此处](/help/components/dimensions/operating-systems.md)），我们估计这将影响不到 3% 的 Chrome 访客。

>[!NOTE]
>
> 截至 2023 年 1 月，某些版本的 Mac 和 Windows 操作系统在用户代理中未正确显示，但在高熵客户端提示中正确表示。 有关更多信息，请参阅[操作系统](/help/components/dimensions/operating-systems.md)。

Adobe Audience Manager需要收集高熵提示以保留完整功能。 如果您正在使用[服务器端转发到Adobe Audience Manager](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)，则您可能希望启用高熵提示的收集。

## 常见问题解答

+++**在哪里可以了解到有关客户端提示的更多信息？**

此 [Google 博文](https://web.dev/user-agent-client-hints/)是一个很好的参考和起点。

+++

+++**如何启用客户端提示的收集？**

浏览器会自动提供低熵提示，这些提示经摄取后用于获取设备和浏览器信息。较新版本的 Web SDK（从 2.12.0 开始）和 AppMeasurement（从 2.23.0 开始）可以配置为通过各自的标记扩展或直接通过配置选项收集高熵提示。请参阅关于 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html#enabling-high-entropy-client-hints?lang=zh-Hans) 和 [AppMeasurement](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) 的说明。

这两个库&#x200B;**在默认情况下禁用**&#x200B;高熵提示的收集。

对于通过 API（例如，通过[数据插入 API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) 或[批量数据插入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)）提交的数据，提示必须明确包含在负载中。请参阅相应文档以了解详细信息。

+++

+++**我是否可以选择收集哪些高熵提示？**

目前还不可以。 您可以选择收集所有高熵提示，或者都不收集。

请注意，当前不收集fullVersionList，因为浏览器主版本被捕获为低熵提示。

+++

+++**各种客户端提示值表示什么？**

下表对截至 2022 年 10 月的客户提示进行了说明。

| 提示 | 描述 | 高熵或低熵 | 示例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | 浏览器和重要版本 | 低 | `"Google Chrome 84"` |
| Sec-CH-UA-Mobile | 移动设备类型（true 或 false） | 低 | `true` |
| Sec-CH-UA-Platform | 操作系统/平台 | 低 | `"Android"` |
| 体系结构 | 网站架构 | 高 | `"arm"` |
| 位数 | 架构位 | 高 | `"64"` |
| fullVersionList | 品牌及其版本的列表 | 高 | `"Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"` |
| model | 设备型号 | 高 | `"Pixel 3"` |
| 平台版本 | 操作系统/平台版本 | 高 | `"10"` |

* 通过请求头收集底熵提示。
* 高熵提示通过 JavaScript 收集并通过查询字符串参数值传递。 查询字符串参数使用`h.`作为图像请求中的前缀。 请注意，当前不收集fullVersionList，因为浏览器主版本被捕获为低熵提示。

高熵提示通过 JavaScript 调用收集并通过查询参数传递

+++

+++**Analytics 中的设备报告是否会有任何变化？**

可用于报告的设备字段不会有任何变化。为这些字段捕获的数据可能会根据为客户端提示配置哪个字段以及如何为客户端提示配置收集而异。

+++

+++**从 User-Agent 获取哪些 Analytics 报告字段？**

这些字段直接从用户-代理派生，但用户-代理可用于帮助派生其他设备相关字段的值，具体取决于设备详细信息。

* [浏览器](/help/components/dimensions/browser.md)
* [浏览器类型](/help/components/dimensions/browser-type.md)
* [操作系统](/help/components/dimensions/operating-systems.md)
* [操作系统类型](/help/components/dimensions/operating-system-types.md)
* [移动设备和移动设备类型](/help/components/dimensions/mobile-dimensions.md)

+++

+++**“冻结”User-Agent 的哪些部分以及何时冻结？** 

请参阅 [Google 发布的时间表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)。此可能会有变化。

+++

+++**Analytics 在哪些方面依赖于用户代理程序？**

报告中的设备信息派生自用户代理程序。 我们更新了我们的流程，以便在可用的情况下同时使用用户代理程序和客户端提示。

回退 ID ([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=zh-Hans)) 派生自用户代理程序和 IP 地址。此 ID 仅在无法设置 Cookie 时使用，因此未被广泛使用

+++

+++**从高熵提示中存储的值获取哪些 Analytics 报告字段？**

随着 Google“冻结”用户代理的更多部分，这将随着时间的推移而改变。第一个受到直接影响的字段是“操作系统”（其中包括操作系统版本）。根据 Google 发布的“冻结”用户-代理提示的时间表，操作系统版本将从 2022 年 10 月底的 Chromium 版本 107 开始冻结。届时，用户代理中的操作系统版本在某些情况下会不准确。

请参阅 [Google 发布的时间表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)以参阅冻结 User-Agent 其他部分的时机。

+++

+++**Adobe 将如何使用客户端提示获取设备信息？**

Adobe 使用第三方 Device Atlas，后者同时使用客户端提示和用户代理程序来派生设备信息。

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

+++**通过Adobe Experience Platform Source Connector发送到Adobe和Customer Journey Analytics的数据中是否会提供客户端提示？**

Adobe 计划在 2023 年上半年在通过 Adobe Source Connector 发送的数据中加入客户端提示。

+++

+++**在 XDM 中如何表示客户端提示？**

请参阅 Adobe Experience Platform 中的[架构文档](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)。

+++

+++**Adobe Audience Manager服务器端转发是否支持客户端提示？** 

是的。客户端提示将包含在转发给Adobe Audience Manager的数据中。 请注意，Adobe Audience Manager需要收集高熵提示以保留完整功能。 如果您正在使用[服务器端转发到Adobe Audience Manager](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)，则您可能希望启用高熵提示的收集。

+++
