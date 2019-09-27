---
description: 'null'
keywords: Data Feed;job;visitors;Experience Cloud ID;analytics visitor id;identify
seo-description: 'null'
seo-title: 识别访客
solution: Analytics
title: 识别访客
topic: Reports and Analytics
uuid: 2490b67e-a333-422d-82fa-cb0670ef2e0c
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 识别访客

Analytics 提供了几种用于识别访客的机制（在[识别访客](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)中列出）。Regardless of the method used to identify a visitor, in data feeds the final visitor ID used by Analytics is split across the `post_visid_high` and `post_visid_low` columns, even when using the Identity Service.

**如何识别独特访客：**

1. Exclude all rows where `exclude_hit > 0`.
1. Exclude all rows with `hit_source = 5,7,8,9`. 5、8 和 9 是使用数据源上载的摘要行。7 表示不应包括在访问和访客计数中的交易 ID 数据源上载。请参阅 [点击来源对照](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42)
1. 结合 `post_visid_high` 使用 `post_visid_low`。 All hits across all dates that contain this combination of `post_visid_high` and `post_visid_low` can be considered as coming from same visitor.

如果您要决定使用哪种机制来确定访客 ID 值（例如，计算接受 Cookie），则 `post_visid_type` 会包含对照关键值来指示所用的 ID 方法。对照关键值在[下表](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A)中随访客 ID 机制一起列出。

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

Experience Cloud ID 在一个单独的列 `mcvisid` 中报告。由于此 ID 在其自身的列中报告，因此无法确定 Analytics 是使用此 ID 还是使用其他 ID 来识别访客。

If the Experience Cloud ID was used to identify the visitor, the ID will be contained in the `post_visid_high` and `post_visid_low` columns and the `post_visid_type` will be set to 5. When calculating metrics, you should use the value from the `post_visid_high` and `post_visid_low` columns since these columns will always contain the final visitor ID.

>[!TIP]
>
> When using the Adobe Analytics visitor ID as a key for other systems, always use `post_visid_high` and `post_visid_low`. 这些字段是唯一能够确保在数据馈送的每一行都有值的访客 ID 字段。

## Analytics 访客 ID {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

在 Analytics 中可通过数种方式来识别访客（在下表中以优先顺序列出）：

| 使用的顺序 | 查询参数（收集方法） | post_visid_type 列值 | 满足条件 |
|---|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) | 0 | s.visitorID 经过设置。 |
| ![](assets/step2_icon.png) | [aid (s_vi cookie)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_analytics.html) | 3 | 在您部署访客 ID 服务或配置访客 ID [宽限期](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html)之前，访客已拥有一个现有的 s_vi Cookie。 |
| ![](assets/step3_icon.png) | [mid (AMCV_ cookie set by Identity Service)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 5 | 访客的浏览器接受cookies（第一方），并部署了标识服务。 |
| ![](assets/step4_icon.png) | [fid（H.25.3 或更新版本，或 AppMeasurement for JavaScript 中的回退 Cookie）](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html) | 4 | 访客的浏览器接受 Cookie（第一方）。 |
| ![](assets/step5_icon.png) | [HTTP 移动订阅者标题](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_mobile.html) | 2 | 设备被识别为移动设备。 |
| ![](assets/step6_icon.png) | [IP 地址、用户代理、网关 IP 地址](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html) | 1 | 访客的浏览器不接受 Cookie。 |

在许多情况下，您可能在一个调用中看到 2 或 3 个不同 ID，但 Analytics 将使用列表中显示的第一个 ID 作为正式访客 ID，并将该值放到 `post_visid_high` 和 `post_visid_low` 列。例如，如果您正在设置一个自定义访客 ID （包含在“vid”查询参数中），那么该 ID 将在同一次点击中出现的其他 ID 之前被使用。
