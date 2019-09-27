---
description: Configuration variables set in AppMeasurement.js.
keywords: Analytics 实施
seo-description: 在AppMeasurement.js for Adobe Analytics中设置的配置变量
seo-title: 配置变量
solution: Analytics
subtopic: 变量
title: 配置变量
topic: 开发人员和实施
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: a340bb50ec437db64dafaddc0b20aec740aee299

---


# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。The most-common configuration variables that are typically set in the main global JavaScript AppMeasurement.js). 这些变量可在Analytics页面级别代码和链接中进行设置（如果适用）。

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. 某些配置变量可能并不适用于您站点的实施需求。

使用这些配置变量的部分目的在于：

* 跟踪多个站点/域。
* 购买时可使用任意货币。
* 捕获不同语言的数据。
* 链接跟踪（已下载文件的数量，指向外部站点的链接）。
* 跟踪自定义链接以实现独特的目的。

>[!NOTE]
>
>[!DNL AppMeasurement] 要求在对跟踪函数的初始调用之前设置所有配置变量 `t()`。 如果在调用后设置了配置变量，则可 `t()`能会出现意外结果。 To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

要获得有关特定配置变量的帮助，请单击以下任意链接：

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):指定存储和报告数据的报表包。

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html):根据每页的URL动态选择报表包。

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html):指定用于确定目标报表包的规则。

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html):使用DOM对象检索所有规则都应用到的URL部分。

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html):为动态填充的变量部署标记。

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html):将传入数据转换为UTF-8，以便Analytics进行存储和报告。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html):确定适用于收入的转化率。

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html):确定设置了哪 `s_cc` 个 `s_sq` 域和cookie。

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html):通过指定页 `s_cc` 面URL `s_sq` 域中的句点数，确定域和Cookie。

* [s.fpCookieDomainPeriods: Specify cookies set by JavaScript (, , plug-ins) that are inherently first-party cookies, even with third-party  or  domains.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html)`s_sq``s_cc``2o7.net``omtrdc.net`

* [s.cookieLifetime: Determine lifespan of a cookie as processed by both JavaScript and data collection servers.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html)

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html): Refer and allow the function to be called at the appropriate location within the JavaScript file.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Function for taking as parameters both the callback (a function), and the parameters to that function.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Function for taking as parameters both the callback (a function), and the parameters to that function.

* [s.trackDownLoadLinks: Track links to downloadable files on your site.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html)

* [s.trackExternalLinks: Determine whether any link clicked is an exit link.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html)

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html): Determine whether ClickMap data is gathered.

* [s.linkDownloadFileTypes: Include a comma-separated list of file extensions.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html)

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkintfilters.html):包括以逗号分隔的过滤器列表，这些过滤器表示站点中的链接。

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html):确定“退出链接”和“文件下载”报告中是否应包含查询字符串。

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html):包含随自定义、退出和下载链接发送的变量列表，以逗号分隔。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html):用于报告特定的退出链接子集。

* [s.usePlugins: Call the  function prior to each image request.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html)`s_doPlugins`

