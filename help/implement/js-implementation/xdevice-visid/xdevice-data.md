---
description: 概述启用跨设备访客识别会对报表中所显示的数据产生怎样的影响。
keywords: Analytics 实施
seo-description: 概述启用跨设备访客识别会对报表中所显示的数据产生怎样的影响。
seo-title: 跨设备访客识别的数据影响
solution: Analytics
subtopic: 访客
title: 跨设备访客识别的数据影响
topic: 开发人员和实施
uuid: 1db4d149-cd50-4b41-a850-988901f25051
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 跨设备访客识别的数据影响

>[!IMPORTANT]
>
>不再建议跨设备识别访客的方法。Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

概述启用跨设备访客识别会对报表中所显示的数据产生怎样的影响。

要解了此功能会对数据收集产生怎样的影响，应清楚访客资料中的访客数据字段：

| 数据字段 | 描述 |
|---|---|
| 访客 ID Cookie | 首次从设备或浏览器访问时自动生成的 ID，存储在 `s_vi` Cookie 中。 |
| 访客 ID 变量 | 可选的[!UICONTROL 访客 ID]，使用 `s.visitorID` 变量进行设置。该值在用户通过验证之后填充，与公司用于在多个数字营销渠道中跟踪用户的 ID 匹配。 |
| 有效访客 ID | 有效的[!UICONTROL 访客 ID] 是访客资料的实际 ID。该值被设置为[!UICONTROL 访客 ID] Cookie 或[!UICONTROL 访客 ID] 变量（如果提供其中一个）。 |

