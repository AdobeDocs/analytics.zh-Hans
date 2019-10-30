---
description: '[!DNL Activity Map]使用更强健的算法跟踪链接，该算法 '
seo-description: '[!DNL Activity Map]使用更强健的算法跟踪链接，该算法 '
seo-title: 可靠的链接跟踪
solution: Analytics
title: 可靠的链接跟踪
topic: Activity Map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# 可靠的链接跟踪

[!DNL Activity Map] 使用更可靠的算法跟踪链接，该算法可：

* 将页面区域的跟踪包括在内，以避免混淆不同设备上的相同链接，因为链接会出现在页面上不同的位置；
* 确保链接的唯一性，即，不能因为链接 ID 的问题或不同浏览器造成的问题，将本不相同的链接误认为同一个链接。

For more on link tracking in [!DNL Activity Map], go [here](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## How [!DNL Activity Map] link tracking may collect PII Data {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION] 通过打开 [!DNL Activity Map] 跟踪功能，您可能正在收集个人识别信息(PII)数据。 通过单独使用这些数据或结合其他信息，可以识别、联系或查找个人，或者在上下文中识别个人。

Here are some known cases where PII data might be collected using [!DNL Activity Map] Tracking:

* `Mailto` 链接。 Mailto 链接是一种 HTML 链接，它可以激活计算机上的默认邮件客户端来发送电子邮件。
* `User ID` 用户登录后，网站的页眉／页脚中可能显示的链接。
* 在金融机构的网站中，账号可能会显示为链接。单击该链接将收集链接的文本。
* 在医疗保健网站中，PII 数据也可能会显示为链接。单击这些链接将收集链接的文本，进而收集 PII 数据。
