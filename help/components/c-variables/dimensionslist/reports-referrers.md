---
title: 反向链接
description: 显示上次点击的 URL（如果该点击位于您的网站之外）。
translation-type: ht
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# 反向链接

“反向链接”维度显示访客到达您的站点前所在的 URL。例如，如果访客点击 `example.com/example-page.html` 上的链接后转至您的网站，则 `example.com/example-page.html` 为反向链接（如果它未定义为属于您的域）。

此维度要求您配置报表包的[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)。如果您未配置内部 URL 过滤器，Adobe Analytics 会将所有域均视为您站点的内部域。

## 维度属性

* 默认情况下，该维使用最近的分配。
* 默认情况下，此维在访问后过期。
* 在（低流量）下对维值进行分组之前，此维受 500k 的唯一限制。Data Warehouse 没有唯一限制。
* 如果某个量度没有反向链接值，则该量度将分组在 `Typed/Bookmarked` 下。
* 此维度通常在首次点击访问时设置，但可以在访问中设置。

## 故障诊断

**问：为什么我发现`googleusercontent.com`是维度值？**

答：[Google](https://about.google/) 将 `googleusercontent.com` 域用于其托管内容。托管内容包括：

* **缓存的页面**：Google Spider 会不断爬网并保存网页，以防它们离线或不可用。通过单击 Google 搜索结果页面中的某个页面的“缓存”链接，所有搜索结果旁边都会出现这些缓存页面。当用户单击此链接后，然后查看您网站上的原始内容时，`googleusercontent.com` 将列为其引用域。这些页面具有子域 `webcache.googleusercontent.com`。
* **翻译页面**：Google 提供了一项强大而便捷的翻译服务。使用此服务查看站点时，服务源自 `googleusercontent.com`。如果用户单击链接以返回到原始内容，反向链接维度将显示此域中的 URL。这些页面具有子域 `translate.googleusercontent.com`。
