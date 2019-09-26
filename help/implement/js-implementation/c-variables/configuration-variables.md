---
description: 在AppMeasurement.js中设置的配置变量。
keywords: Analytics 实施
seo-description: 在AppMeasurement.js for Adobe Analytics中设置的配置变量
seo-title: 配置变量
solution: Analytics
subtopic: 变量
title: 配置变量
topic: 开发人员和实施
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。最常见的配置变量通常在主全局JavaScript appMeasurement.js中设置。 这些变量可在Analytics页面级别代码和链接中进行设置（如果适用）。

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. 某些配置变量可能并不适用于您站点的实施需求。

使用这些配置变量的部分目的在于：

* 跟踪多个站点/域。
* 购买时可使用任意货币。
* 捕获不同语言的数据。
* 链接跟踪（已下载文件的数量，指向外部站点的链接）。
* 跟踪自定义链接以实现独特的目的。

>[!NOTE]
>
>[!DNL AppMeasurement] requires that all configuration variables are set before the initial call to the track function, `t()`. 如果在调用后设置了配置变量，则可 `t()`能会出现意外结果。 To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

有关特定配置变量的帮助，请参阅以下链接：

* [s_account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specify the report suite where data is stored and reported.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Dynamically select the report suite based on the URL of each page.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):指定用于确定目标报表包的规则。

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):使用DOM对象检索所有规则都应用到的URL部分。

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):为动态填充的变量部署标记。

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):将传入数据转换为UTF-8，以便Analytics进行存储和报告。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):确定适用于收入的转化率。

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):确定设置了哪 `s_cc` 个 `s_sq` 域和cookie。

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):通过指定页 `s_cc` 面URL `s_sq` 域中的句点数，确定域和Cookie。

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):指定由JavaScript(`s_sq`、 `s_cc`插件)设置的内在是第一方Cookie的Cookie，即使是第三方或域 `2o7.net` 也是 `omtrdc.net` 如此。

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):确定JavaScript和数据收集服务器处理的Cookie的寿命。

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):引用并允许在JavaScript文件中的适当位置调用该函数。

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):用作回调（函数）和该函数的参数的函数。

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):用作回调（函数）和该函数的参数的函数。

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):跟踪网站上可下载文件的链接。

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):确定单击的任何链接是否为退出链接。

* [strackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):确定是否收集ClickMap数据。

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):包含以逗号分隔的文件扩展名列表。

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Includes a comma-separated list of filters that represent the links that are part of the site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine whether or not the query string should be included in the Exit Links and File Download reports.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):包含随自定义、退出和下载链接发送的变量列表，以逗号分隔。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):用于报告特定的退出链接子集。

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):在每个图 `s_doPlugins` 像请求之前调用函数。

