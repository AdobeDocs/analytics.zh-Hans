---
description: 配置变量是在 AppMeasurement.js 中设置的。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 配置变量
topic: Developer and implementation
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: bc8d4e922a776596c9af83a1cd6e22f8967ef2d0

---


# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。最常见的配置变量通常在主全局JavaScript appMeasurement.js中设置。 适当的时候，可以在 Analytics 页面级代码和链接中设置这些变量。

通过&#x200B;**[!UICONTROL 管理工具]** &gt; **[!UICONTROL 代码管理器]**&#x200B;生成代码时，默认情况下，并非所有这些变量都会显示在代码中。其中某些配置变量可能不适用于您的站点实施需求。

使用这些配置变量的部分目的在于：

* 跟踪多个站点／域
* 购买时使用任何货币
* 捕获不同语言的数据
* 链接跟踪（下载的文件数，到外部站点的链接）。
* 跟踪自定义链接以实现独特目的

> [!NOTE][!DNL AppMeasurement] 要求所有配置变量都必须在初次调用跟踪函数 `t()` 之前设置。如果在调用 `t()` 之后设置配置变量，可能会发生意外结果。为确保正常的数据收集，所有配置变量都必须位于 `doPlugins` 函数上方。

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

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html):指定由JavaScript(`s_sq`、 `s_cc`插件)设置的内在是第一方Cookie的Cookie，即使是第三方或域 `2o7.net` 也是 `omtrdc.net` 如此。

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html):确定JavaScript和数据收集服务器处理的Cookie的寿命。

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html):引用并允许在JavaScript文件中的适当位置调用该函数。

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html):用作回调（函数）和该函数的参数的函数。

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html):跟踪网站上可下载文件的链接。

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html):确定单击的任何链接是否为退出链接。

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html):确定是否收集ClickMap数据。

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html):包含以逗号分隔的文件扩展名列表。

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackintfilters.html):包括以逗号分隔的过滤器列表，这些过滤器表示站点中的链接。

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html):确定“退出链接”和“文件下载”报告中是否应包含查询字符串。

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html):包含随自定义、退出和下载链接发送的变量列表，以逗号分隔。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html):用于报告特定的退出链接子集。

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html):在每个图 `s_doPlugins` 像请求之前调用函数。

* [s.useForcedlinkTracking](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-usedforcedlinktracking.html):禁用某些浏览器的强制链接跟踪。

* [s.linkType](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktype.html):将链接类型设置为下载、退出或自定义。

* [s.linkName](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html):设置在下载、退出或自定义链接报告中显示的名称。

* [s.ForcedlinkTrackingTimeout](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-forcedlinktrackingtimeout.html):设置跟踪时的最大等待时间。

* [s.linkTrackEvents](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackingevents.html):禁用某些浏览器的强制链接跟踪。

* [s.linkUrl](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkurl.html):设置链接的URL。

* [s.linkObject](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkobject.html):引用已单击的对象。
