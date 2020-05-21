---
title: 退出链接
description: 报告用户单击离开网站时最常使用的链接。
translation-type: ht
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# 退出链接

显示用户单击离开网站时最常使用的链接。这些链接通常指向合作伙伴或关联站点；但是，它们可以是具有外部链接的任何位置。您可以使用此报表来查看最热门的附属链接，或帮助验证您的合作伙伴声称您提供的反向链接数量。

要正确填充此页面，必须满足几项要求：
* 如果使用手动自定义链接跟踪，则必须在中间参数设置为 `e` 时触发 `tl()` 请求。
* 如果使用自动自定义链接跟踪，则必须满足所有要求：
   * 必须启用 [trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) 变量。
   * 用户单击的链接不得与 [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) 变量中的任何值匹配。
   * 如果存在 [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) 变量，则外部链接必须至少与此变量中设置的一个值匹配。
* 如果不满足以上任何一个要求，点击都不会填充此报表。
* 与所有自定义链接跟踪点击一样，从图像请求中删除了 [pageName](/help/implement/vars/page-vars/pagename.md) 变量，以防止对页面查看次数量度虚增。
* 您可以通过趋势和排名两种格式查看此报表。
* 此报表可使用搜索过滤器来查找特定的行项目。
* 您可以通过任何其他变量创建[划分](/help/analyze/reports-analytics/reports-customize/breakdowns.md)。
