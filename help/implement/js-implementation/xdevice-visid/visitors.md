---
description: Analytics 将每个有效的独特访客 ID 算作一个独特访客。
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: 访客
topic: Developer and implementation
uuid: 16cfdb64-a3c6-4056-97da-3227cddcf1cd
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 访客

>[!IMPORTANT]
>
>不再建议使用这种方法来识别跨设备访客。请参阅 [Adobe Experience cloud设备协作文档](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

Analytics 将每个有效的独特访客 ID 算作一个独特访客。

如果查看[前表](/help/implement/js-implementation/xdevice-visid/visit-example.md)，就会发现同一访客被计算了 3 次：即第 1、9 和 10 次点击。这是因为这两个服务器调用的有效[!UICONTROL 访客 ID] 相同，而且即使两次访问相隔几个小时并且发生在不同的设备上，也会这样处理。

在启用跨设备访客识别时，这可能会增加您所看到的独特访客数。同一次访问中访客可能会被计算两次：首次访问被计算一次，用户通过验证后又被计算一次。

当新访客查看您的网站时，将填充并存储 `s_vi` Cookie。在数据收集服务器上，将为此访客 ID 创建新访客资料，并将资料中的有效[!UICONTROL 访客 ID] 设置为与 Cookie 匹配。

在启用跨设备访客识别时，如果随后的点击（如验证后）中提供了[!UICONTROL 访客 ID] 变量，则会更新有效[!UICONTROL 访客 ID] 以与自定义值匹配。这可能会致使有效[!UICONTROL 访客 ID] 在验证后直接发生更改，从而产生多个访客计数。

![](assets/visitors.png)

首次关联之后，访问次数恢复正常，因为访客通过[!UICONTROL 访客 ID] Cookie 进行关联。如果访客稍后查看您的网站，接着进行验证，访客计数不会虚增，因为有效的[!UICONTROL 访客 ID] 在验证后不会发生更改。

![](assets/visitors_2.png)

