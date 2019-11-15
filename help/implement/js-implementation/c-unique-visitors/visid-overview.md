---
description: Adobe 使用 Cookie 来跟踪独特的浏览器/设备。
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: 识别独特访客
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 识别独特访客

Adobe 使用 Cookie 来跟踪独特的浏览器/设备。

## Analytics 访客 ID 订购 {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics 提供了多种识别访客的机制。下表列出了在 Analytics 中识别访客的不同方法（按照优先级排序）：

| 使用顺序 | 查询参数（收集方法） | 显示条件 |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](/help/implement/js-implementation/c-unique-visitors/visid-custom.md) | 设置了 s.visitorID |
| ![](assets/step2_icon.png) | [aid (s_vi cookie)](/help/implement/js-implementation/c-unique-visitors/visid-analytics.md) | 在您部署访客 ID 服务或配置访客 ID 宽限期之前，访客已拥有一个现有的 s_vi Cookie。 |
| ![](assets/step3_icon.png) | [mid（由 Experience Cloud 访客 ID 服务设置的 AMCV_ Cookie）](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 访客的浏览器接受 Cookie（第一方） |
| ![](assets/step4_icon.png) | [fid（H.25.3 或更高版本上的回退 Cookie，或者 AppMeasurement for JavaScript）](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md) | 访客的浏览器接受 Cookie（第一方） |
| ![](assets/step5_icon.png) | [IP 地址、用户代理、网关 IP 地址](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | 访客的浏览器不接受 Cookie。 |

在许多情况下，您可能会在一次调用中看到 2 或 3 个不同的 ID，但是 Analytics 会将上表中出现的第一个 ID 用作正式的访客 ID。例如，如果您正在设置一个自定义访客 ID （包含在“vid”查询参数中），那么该 ID 将在同一次点击中出现的其他 ID 之前被使用。

> [!NOTE]每个 Analytics 访客 ID 均与 Adobe 服务器上的一个访客资料关联。无论任何访客 ID Cookie 是否过期，访客资料在处于至少 13 个月的非活动状态之后会被删除。
