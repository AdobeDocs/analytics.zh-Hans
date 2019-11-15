---
description: 'Activity Map 利用更加可靠的算法来跟踪链接 '
solution: Analytics
title: 可靠的链接跟踪
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 可靠的链接跟踪

Activity Map 利用更加可靠的算法来跟踪链接:

* 将页面区域的跟踪包括在内，以避免混淆不同设备上的相同链接，因为链接会出现在页面上不同的位置；
* 确保链接的唯一性，即，不能因为链接 ID 的问题或不同浏览器造成的问题，将本不相同的链接误认为同一个链接。

有关 Activity Map 中链接跟踪的更多信息，请转至[此处](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)。

## Activity Map 链接跟踪如何收集 PII 数据 {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION] 启用 Activity Map 跟踪后，您可能会收集个人身份识别信息 (PII) 数据。此类数据可用于（单独或与其他信息配合使用）识别、联系或查找个人，或者在上下文中识别个人。

以下是使用 Activity Map 跟踪收集 PII 数据的一些已知案例：

* `Mailto` 链接。Mailto 链接是一种 HTML 链接，它可以激活计算机上的默认邮件客户端来发送电子邮件。
* 用户登录后可能出现在网站页眉/页脚的 `User ID` 链接。
* 在金融机构的网站中，账号可能会显示为链接。单击该链接将收集链接的文本。
* 在医疗保健网站中，PII 数据也可能会显示为链接。单击这些链接将收集链接的文本，进而收集 PII 数据。
