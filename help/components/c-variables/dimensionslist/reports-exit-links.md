---
title: 退出链接
description: 报告用户单击离开网站时最常使用的链接。
translation-type: tm+mt
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# 退出链接

显示用户单击离开网站时最常使用的链接。 这些链接通常指向合作伙伴或附属网站；但是，它们可以是具有外部链接的任何位置。 您可以使用此报表来查看最热门的附属链接，或帮助验证您的合作伙伴声称您提供的反向链接数量。

要正确填充此页面，必须满足几项要求：
* 如果使用手动自定义链接跟踪， `tl()` 则必须触发请求并将中间参数设置为 `e`。
* 如果使用自动自定义链接跟踪，则必须满足所有要求：
   * 必 [须启用trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) 变量。
   * The link the user clicked on must not match any values within the [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) variable.
   * If the [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) variable exists, the external link must match at least one of the values set in this variable.
* 如果未满足上述任何要求，则点击不会填充此报表。
* 与所有自定义链接跟踪点击一样， [pageName](/help/implement/vars/page-vars/pagename.md) 变量会从图像请求中去除，以防止页面视图量度出现通胀。
* 您可以通过趋势和排名两种格式查看此报表。
* 此报表可使用搜索过滤器来查找特定的行项目。
* 您可以通过管理工具创建与其他任何流量变量的 用 [其他](/help/analyze/reports-analytics/reports-customize/breakdowns.md) 变量进行细分。
