---
description: 显示您网站的访客喜爱的链接。例如，您的网站主页可能有多个显示同一页面的链接。可能有链接至同一页面的图形和文本链接。此报表显示使用图形链接与使用文本链接的访客百分比。
title: 自定义链接
topic: Reports
uuid: 2e0d0175-d5e4-4919-b601-3f488ef3e090
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 自定义链接

显示您网站的访客喜爱的链接。例如，您的网站主页可能有多个显示同一页面的链接。可能有链接至同一页面的图形和文本链接。此报表显示使用图形链接与使用文本链接的访客百分比。

您要跟踪的特定链接必须使用特殊标记进行修改，请参阅[链接跟踪](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)。

[!UICONTROL 自定义链接报表]的用途包括：

* 了解您的访客喜爱的链接类型，优化网站设计
* 验证对单一页面采用多余链接的必要性

## Mobile SDK 链接名称 {#section_70C91FE794104B5FBF289B19CC02EA8E}

[Mobile SDK](https://marketing.adobe.com/resources/help/zh_CN/mobile/home.html) 使用自定义链接来跟踪操作和生命周期量度。在用于测量移动设备应用程序的报表包中，您可能看到由 SDK 设置的下列链接名称：

| ADBINTERNAL:Lifecycle | 由 4.x SDK 中的生命周期调用发送。 |
|---|---|
| AMACTION:[操作名称] | 由 4.x SDK 中的 trackAction() 方法发送，其中操作名称是调用该方法时设置的名称。 |
| ADMS BP 事件 | 由 3.x SDK 中的生命周期调用发送。 |

