---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: 更新您的 DFA 查询字符串参数
solution: Analytics
title: 更新您的 DFA 查询字符串参数
topic: Data connectors
uuid: adf585ac-84ff-44c1-a48 d-b072726 c8494
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 更新您的 DFA 查询字符串参数{#update-your-dfa-query-string-parameter}

如果您在 DFA 集成之前已通过 Adobe Analytics 跟踪广告促销活动，则有可能所有促销活动（电子邮件、搜索或横幅）均使用相同的查询字符串参数来标识登陆页面上的反向链接促销活动 ID。

要弄清何时为您的 DFA 广告促销活动请求来自 DFA 数据的显示到达和点进数据，Data connectors 需要在访客点击某 DFA 促销活动横幅广告时进行标识。要做到这一点，您必须在 DFA 广告促销活动的登陆页面 URL 中添加一个差异化的查询字符串参数，这样 Data connectors 就能够区分 DFA 广告促销活动页面和您的网站上可能存在的其他广告促销活动页面。The `dfa_overrideParam` in the JavaScript plug-in (see [Update Your Web Site's Data Collection Code](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) used for DFA.

>[!CAUTION]
>
>尽管Campaign变量可用于其他营销活动，但不要将其用于DFA系列活动。如果您将促销活动变量设置为 DFA 促销活动登陆页面，则 Adobe 无法将展示次数和点击量关联到 DFA 促销活动点进次数。每次访问后，Adobe 收集服务器都会检查 DFA 服务器中的上一次点进或显示到达。因此，将只在常用登陆页面中包含 DFA 插件代码（请参阅[更新网站的数据收集代码](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)），以避免不必要的重定向，这些重定向会减缓页面加载时间，这对于 Internet 连接速度较慢的用户尤其不便。

