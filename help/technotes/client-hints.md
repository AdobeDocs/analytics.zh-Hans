---
title: 客户端提示
description: 了解客户端提示如何逐渐取代用户代理作为设备信息源。
source-git-commit: 72ef2d5e34220f1703714fac40a9dae4e76c1ab1
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---


# 客户端提示概述和常见问题解答

客户端提示是有关用户设备的个别信息。 它们由Google Chrome和Microsoft Edge等Chromium浏览器提供。 对于这些浏览器，客户端提示将逐渐取代用户代理作为设备信息源。 Adobe Analytics将更新其设备查找过程，以便除用户代理之外，还使用客户端提示来确定设备信息。

Google将用户代理客户端提示分为两类：低熵和高熵提示。

* **低熵提示** 包含有关设备的更多常规信息。 这些提示由Chromium浏览器自动提供。

* **高熵** 提示包含更多详细信息。 这些提示仅可通过请求使用。 AppMeasurement和Web SDK [可以配置](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) 请求高熵提示。 默认情况下，两个库都会 **not** 请求高熵提示。

>[!NOTE]
>
>从2022年10月开始，新版Chromium浏览器将开始“冻结”用户代理字符串中表示的操作系统版本。 当用户升级其设备时，用户代理中的操作系统不会发生更改。 因此，随着时间的推移，用户代理中表示的操作版本信息将变得不那么准确。 操作系统版本是一个高熵提示，因此要在报表中保持操作系统版本的准确性，必须配置您的收集库以收集这些高熵提示。 随着时间的推移，用户代理的其他设备信息将被冻结，需要客户端提示来保持设备报告的准确性。

## 常见问题解答

+++**我可以在哪里了解有关客户端提示的更多信息？**

此 [Google博客文章](https://web.dev/user-agent-client-hints/) 是一个很好的参考和起点。

+++

+++**如何启用客户端提示的集合？**

低熵提示由浏览器自动提供并包含在Adobe的获取设备和浏览器信息的过程中。 可以将较新版本的AppMeasurement(从2.23.0开始)和Web SDK(从2.12.0开始)配置为收集高熵提示。 对于这两个库，高熵提示的集合是 **默认情况下处于禁用状态**.

+++

+++**如何捕获高熵提示？**

高熵提示可以通过Web SDK和AppMeasurement库各自的标记扩展配置，也可以直接使用collectHighEntropyUserAgentHints标记配置。

+++

+++**我可以选择我收集的高熵提示吗？**

现在不行。 您可以选择收集所有高熵提示，也可以选择不收集任何提示。

+++

+++**Analytics中的设备报表是否会发生任何更改？**

可用于报告的设备字段不会更改。 根据为客户端提示配置集合的字段和方式，为这些字段捕获的数据可能会发生更改。

+++

+++**哪些Analytics报表字段是从用户代理派生的？**

* [浏览器](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [浏览器类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [操作系统](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [操作系统类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [移动设备和移动设备类型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)
* [数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans)

+++

+++**哪些Analytics报表字段是从高熵提示中存储的值派生的？**

自2022年9月起，Google发布的“冻结”用户代理提示时间表指示操作系统版本将从2022年10月起停止更新。 当用户升级其操作系统时，用户代理中的操作系统版本将不会更新。 如果没有高熵提示，操作系统版本（包含在Analytics“操作系统”维度中）的准确性将逐渐降低。

请参阅 [Google发布的时间轴](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) 查看冻结用户代理其他部分的时间。

+++

+++**Adobe如何使用客户端提示获取设备信息？**

Adobe使用第三方Device Atlas，Device Atlas将同时使用客户端提示和用户代理获取设备信息。

+++

+++**客户端提示会影响哪些浏览器？**

客户端提示仅适用于Chromium浏览器，如Google Chrome和Microsoft Edge。 其他浏览器或移动设备应用程序中的数据没有变化。

+++

+++**客户端提示是否会在通过Adobe源连接器发送到AEP和CJA的数据中可用？**

2023年上半年，我们计划通过Adobe源连接器在数据中包含客户端提示。

+++

+++**XDM中如何显示客户端提示？**

请参阅 [模式文档](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) 在Adobe Experience Platform。

+++

+++**有哪些提示字段？ 哪些会影响设备报表？**

下表介绍了自2022年9月起的客户提示。

| 提示 | 描述 | 高或低熵 | 示例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | 浏览器和重要版本 | 低 | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | 移动设备（true或false） | 低 | TRUE |
| Sec-CH-UA-Platform | 操作系统/平台 | 低 | &quot;Android&quot; |
| Sec-CH-UA-Arch | 网站的架构 | 高 | &quot;arm&quot; |
| Sec-CH-UA-Bitness | 架构位 | 高 | &quot;64&quot; |
| Sec-CH-UA-Full-Version | 浏览器的完整版本 | 高 | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | 品牌及其版本列表 | 高 | &quot;Not A;Brand&quot;;v=&quot;99&quot;,&quot;Chromium&quot;;v=&quot;98&quot;,&quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | 设备型号 | 高 | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | 操作系统/平台版本 | 高 | &quot;10&quot; |

+++



+++**用户代理的哪些部分被“冻结”？何时？**

请参阅 [Google发布的时间轴](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). 这可能会发生变化。

+++
