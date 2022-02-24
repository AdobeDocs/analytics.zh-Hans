---
title: 反向链接域
description: 访客在点击进入到您的网站之前所处的首要域。
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '493'
ht-degree: 100%

---

# 反向链接域

“反向链接域”维度报告访客通过点击哪些域才得以访问您的网站。此维度有助于了解哪些第三方网站给您的网站带来了最多的流量。链接必须存在于外部网站上，且访客必须单击该链接才能显示维度项目。

>[!IMPORTANT]
>
>必须配置报表包的[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)，才能使用此维度。无法配置内部 URL 过滤器，可能会包含内部域或阻止出现外部域。

同一报表在 Analysis Workspace 和 Data Warehouse 中可能会显示不同的结果。Analysis Workspace 会报告每个页面的反向链接域，但不包括与内部 URL 过滤器匹配的值。Data Warehouse 则仅报告访问的第一个反向链接域，并且会忽略内部 URL 过滤器。

## 使用数据填充此维度

此维度需要在 Analytics 界面中进行配置，并获取图像请求中的数据。

* 在实施中，此维度从图像请求中的 [`r` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用浏览器中的 JavaScript 变量 `document.referrer` 收集此数据。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在图像请求中包含 `r` 查询字符串参数。
* 在 Analytics 界面中，必须配置报表包的[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)。无法配置内部 URL 过滤器，可能会包含内部域或阻止出现外部域。

Adobe 继续提供访问的反向链接域。如果访客离开并在单次访问中点击不同域上的链接，则新值会更新并且在剩余的访问时间内持续存在。如果只想查看原始值，请参阅[原始反向链接域](original-referring-domain.md)。

## 维度项目

维度项目包括访客点击进入您的网站的域。如果点击没有任何反向链接数据（设置或保留），则它会分组到维度项目 `"Typed/Bookmarked"` 下。此维度项目表示不存在反向链接值，例如，如果访客在地址栏中手动键入浏览器地址，或单击书签。对于不适用于 Analytics 的重定向，也会显示 `"Typed/Bookmarked"` 维度项目。请参阅技术说明用户指南中的[重定向和别名](/help/technotes/redirects.md)。

### 包含 `googleusercontent.com` 的维度项目

用户可以查看包含域 `googleusercontent.com` 的维度项目。

* **缓存的页面**：Google Spider 会不断地抓取网页并存储页面副本，以防它们离线。在大多数搜索结果旁边，通过单击“已缓存”链接，即可使用这些缓存的页面。当用户单击此链接并查看 Google 缓存的内容时，`googleusercontent.com` 是维度项目。
* **翻译页面**：Google 提供了一项强大而便捷的翻译服务。使用此服务查看站点时，服务源自 `googleusercontent.com`。如果用户单击某个链接以返回到原始内容，则会显示此维度项目。
