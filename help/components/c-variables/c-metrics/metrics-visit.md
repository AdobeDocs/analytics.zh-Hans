---
description: 表示一系列的页面查看操作。访问量度通常用在显示选定时段内用户会话数量的报表中。
keywords: 访问
seo-description: 表示一系列的页面查看操作。访问量度通常用在显示选定时段内用户会话数量的报表中。
seo-title: 访问
solution: Analytics
title: 访问
topic: 量度
uuid: 91317487-f116-4546-8cd2-421418c49 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a7 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 访问

表示一系列的页面查看操作。访问量度通常用在显示选定时段内用户会话数量的报表中。

>[!NOTE]
>
>For information about how visits and mobile app launches are calculated, see [Compare Visits and Mobile App Launches](https://helpx.adobe.com/analytics/kb/compare-visits-and-mobile-app-launches.html) in the Knowledge Base.

访问量度始终与某个时段关联，因此当同一访客返回您的站点时，您可以知道是否将其认为是新的访问。会话在用户首次到达您的网站时开始，并在遇到以下情况之一时结束：

* **非活动状态持续 30 分钟：**&#x200B;几乎所有会话都以这种形式结束。如果前后图像请求之间经过了 30 分钟以上，则开始一次新的访问。
* **活动状态持续 12 个小时：**&#x200B;如果用户触发图像请求达 12 个小时且从未超过 30 分钟的间隔，则自动开始一次新的访问。
* **2500 次点击：**&#x200B;如果用户在不启动新会话的情况下生成大量的点击次数，那么在 2500 次图像请求后会认为是新的访问。
* **100 秒内 100 次点击**：如果某次访问在 100 秒内有超过 100 次点击，那么该次访问将自动结束。此行为通常是机器人行为，我们会强制执行该限制，以避免这些频繁处理的访问造成延迟增加以及生成报表的时间增加。

>[!NOTE]
>
>如果特别请求，可以缩短访问定义的定义，但无法延长。请让贵组织的一位受支持用户联系客户关怀，以请求此更改。

在遇到以下情况时，不会开始新的访问：

* 用户关闭标签，又将其重新打开，然后在 30 分钟内返回您的网站。用户还可以关闭浏览器，或者重新启动计算机，但仍会被计为单次访问（如果访客在 30 分钟内返回您的网站）。
* 用户在多个标签中浏览您的网站。虽然多标签浏览不会增加访问量或访客数，但使用单独的浏览器会增加这些数据。这是因为不同的标签引用的是相同的 Cookie，而不同的浏览器则不是。

访问不一定等同于浏览器会话。例如，如果访客关闭浏览器，再重新打开浏览器，并在 5 分钟后访问网站，则仍将其视为同一次访问。这也意味着如果访客持续 35 分钟停留在一个网页上，那么此访问将被关闭并进行处理，如果该访客点进了其他页面，则会开始一个新的访问。

当某访问结束时，与该访问到期有关的所有变量都将过期，并且不再持续存在。访问量量度将在该访客的下次访问时递增。

>[!NOTE]
>
>If you are using Analytics as the reporting source for Adobe Target, refer to [Minimizing Inflated Visit and Visitor Counts in A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) in the [!DNL Target] documentation.

有关详细信息，请参阅《Adobe Analytics 实施指南》中的[识别独特访客](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_overview.html)。

**时段**

在发生活动的每个时间段内都会报告一次访问。例如，假设某个访问在 12 月 1 日晚上 11:45 开始，并且持续到 12 月 2 日凌晨 12:30。该访问在 12 月 1 日和 12 月 2 日被计入。此报告也适用于其他时段，包括每周、每月、每季度和每年。
