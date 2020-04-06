---
description: 'Activity Map 利用更加可靠的算法来跟踪链接 '
title: 可靠的链接跟踪
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 可靠的链接跟踪

Activity Map 利用更加可靠的算法来跟踪链接:

* 包括对页面区域的跟踪，以避免同一链接在不同设备之间出现混淆的情况，因为该链接显示在页面上的不同位置；
* 确保链接的唯一性，即不能因LinkID问题或跨不同浏览器创建的不同链接而将不同链接误认为一个链接。

有关活动图中链接跟踪的更多信息，请转 [到此处](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)。

## Activity Map 链接跟踪如何收集 PII 数据 {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION] 启用 Activity Map 跟踪后，您可能会收集个人身份识别信息 (PII) 数据。此类数据可用于（单独或与其他信息配合使用）识别、联系或查找个人，或者在上下文中识别个人。

以下是使用 Activity Map 跟踪收集 PII 数据的一些已知案例：

* `Mailto` 链接。Mailto 链接是一种 HTML 链接，它可以激活计算机上的默认邮件客户端来发送电子邮件。
* 用户登录后可能出现在网站页眉/页脚的 `User ID` 链接。
* 对于金融机构，帐号可能显示为链接。单击帐号即会收集链接的文本。
* 医疗网站也可能将 PII 数据显示为链接。单击此类链接即会收集链接的文本，从而收集 PII 数据。
