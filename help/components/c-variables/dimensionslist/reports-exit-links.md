---
description: 显示人们最常单击的、导向网站外部的链接。这些链接通常指向合作伙伴或附属网站。但是，它们可以是您实施外部链接的任意位置。您可以使用此报表来查看最热门的附属链接，或帮助验证您的合作伙伴声称您提供的反向链接数量。
seo-description: 显示人们最常单击的、导向网站外部的链接。这些链接通常指向合作伙伴或附属网站。但是，它们可以是您实施外部链接的任意位置。您可以使用此报表来查看最热门的附属链接，或帮助验证您的合作伙伴声称您提供的反向链接数量。
seo-title: 退出链接
solution: Analytics
title: 退出链接
topic: 报表
uuid: e1452f04-389d-4aa3-8673-732880284302
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 退出链接

显示人们最常单击的、导向网站外部的链接。这些链接通常指向合作伙伴或附属网站。但是，它们可以是您实施外部链接的任意位置。您可以使用此报表来查看最热门的附属链接，或帮助验证您的合作伙伴声称您提供的反向链接数量。

要正确填充此页面，必须满足几项要求：

* 如果使用手动自定义链接跟踪，必须触发&#x200B;*`s.tl()`*&#x200B;请求，同时中间的参数应设置为 *e*。

* 如果使用自动自定义链接跟踪，则必须满足所有要求：
* 

   * [s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_trackexlinks) 必须设置为 *true*。

   * 用户单击的链接不得与 [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters) 变量中的任何值匹配。
   * 如果实施了 [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters)，则外部链接必须至少与此变量中设置的一个值匹配。

* 如果不满足以上任何一个要求，点击都不会填充此报表。

* 
* 与所有自定义链接跟踪点击一样，[s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_pagename) 变量将会从图像请求中去除，以防止页面查看虚增。
* 您可以通过趋势和排名两种格式查看此报表。
* 此报表可使用搜索过滤器来查找特定的行项目。
* 您可以通过管理工具创建与其他任何流量变量的[通过](/help/analyze/reports-analytics/reports-customize/breakdowns.md) Admin Tools与任何其他变量进行细分。
* [实例](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)是唯一默认可在此报表中使用的量度，用于计数触发退出链接的次数。
* 可以为此报表启用每日、每周、每月和每季访客。但是，只有 Adobe 代表可以启用这些量度，并且需要支付额外的成本。为任何自定义链接跟踪变量启用独特访客会大大增加报表包的滞后。

