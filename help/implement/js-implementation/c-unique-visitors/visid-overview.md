---
description: Adobe 使用 Cookie 来跟踪独特的浏览器/设备。
keywords: Analytics 实施
seo-description: Adobe 使用 Cookie 来跟踪独特的浏览器/设备。
seo-title: 识别独特访客
solution: Analytics
subtopic: 访客
title: 识别独特访客
topic: 开发人员和实施
uuid: ed4dee75-ecfb-4715-8122-461983c7 dd8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 识别独特访客

Adobe 使用 Cookie 来跟踪独特的浏览器/设备。

## Analytics 访客 ID 订购 {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics 提供了多种识别访客的机制。下表列出了在 Analytics 中识别访客的不同方法（按照优先级排序）：

| 使用顺序 | 查询参数（收集方法） | 显示条件 |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](../../../implement/js-implementation/c-unique-visitors/visid-custom.md#concept_4A2000F4B6ED41E99CA6118A6D74ECE8) | 设置了 s.visitorID |
| ![](assets/step2_icon.png) | [aid (s_vi cookie)](../../../implement/js-implementation/c-unique-visitors/visid-analytics.md#concept_74F6B4B9B2FA415AB5D029A1F8F099BC) | 在您部署访客 ID 服务或配置访客 ID 宽限期之前，访客已拥有一个现有的 s_vi Cookie。 |
| ![](assets/step3_icon.png) | [mid（由 Experience Cloud 访客 ID 服务设置的 AMCV_ Cookie）](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 访客的浏览器接受 Cookie（第一方） |
| ![](assets/step4_icon.png) | [fid（H.25.3 或更高版本上的回退 Cookie，或者 AppMeasurement for JavaScript）](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#concept_EBCBF9EB390E45A2BA20DB6BE931C505) | 访客的浏览器接受 Cookie（第一方） |
| ![](assets/step5_icon.png) | [IP 地址、用户代理、网关 IP 地址](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | 访客的浏览器不接受 Cookie。 |

在许多情况下，您可能会在一次调用中看到 2 或 3 个不同的 ID，但是 Analytics 会将上表中出现的第一个 ID 用作正式的访客 ID。例如，如果您正在设置一个自定义访客 ID （包含在“vid”查询参数中），那么该 ID 将在同一次点击中出现的其他 ID 之前被使用。

>[!NOTE]
>
>每个Analytics访客ID与Adobe服务器上的访客配置文件相关联。无论任何访客 ID Cookie 是否过期，访客资料在处于至少 13 个月的非活动状态之后会被删除。
