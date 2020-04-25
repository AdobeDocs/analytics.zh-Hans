---
title: 反向链接
description: 显示上一次点击的URL（如果该点击在您的站点之外）。
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# 反向链接

“推荐人”维显示访客到达您的站点前的来源URL。 For example, if a visitor clicks a link from `example.com/example-page.html` and arrives on your site, `example.com/example-page.html` is the referrer if it is not defined as part of your domain.

此维度要求您配置报表包的内 [部URL过滤器](/help/admin/admin/internal-url-filter-admin.md)。 如果您不配置内部URL过滤器,Adobe Analytics会将所有域视为站点的内部。

## 维属性

* 默认情况下，此维使用最近的分配。
* 默认情况下，该维在访问后过期。
* 在（低流量）下分组维值之前，此维受500k的唯一限制。 数据仓库没有唯一的限制。
* 如果某个度量没有推荐人值，则该度量将分组在下 `Typed/Bookmarked`。
* 此维度通常在访问的第一次点击时设置，但可以在访问中设置。

## 故障诊断

**问：为什么我将`googleusercontent.com`其视为维值？**

答： [Google](https://about.google/) 将域用于 `googleusercontent.com` 其托管内容。 托管内容包括：

* **缓存的页面**:Google的蜘蛛程序会不断地爬网并保存网页，以防网页离线或不可用。 通过单击Google搜索结果页面之一中的“缓存”链接，所有搜索结果旁边都有这些缓存的页面。 当用户单击此链接后，查看站点上的原始内容， `googleusercontent.com` 即列为其引用域。 这些页面具有子域 `webcache.googleusercontent.com`。
* **译文页面**:Google优惠了一项强大而便捷的翻译服务。 使用此服务查看站点时，它来自 `googleusercontent.com`。 如果用户单击链接以返回到原始内容，推荐人维将显示此域的URL。 这些页面具有子域 `translate.googleusercontent.com`。
