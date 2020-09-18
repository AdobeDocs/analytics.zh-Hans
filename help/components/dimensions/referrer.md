---
title: 反向链接
description: 访客在点击进入到您的网站之前所在的 URL。
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 48%

---


# 反向链接

“反向链接”维度会报告访客点击访问您的网站前所在的 URL。此维度有助于了解哪些特定 URL 给您的网站带来了最多的流量。外部URL上必须存在链接，访客必须单击该链接才能显示维度项。

>[!IMPORTANT]
>
>必须配置报表包的[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)，才能使用此维度。无法配置内部 URL 过滤器，可能会包含内部 URL 或阻止出现外部 URL。

同一份报告显示Analysis Workspace和Data warehouse的结果不同。 Analysis Workspace报告每个页面的推荐人，但不包括与内部URL过滤器匹配的值。 data warehouse仅报告访问的第一个推荐人，并忽略内部URL过滤器。

## 使用数据填充此维度

此维度需要在 Analytics 界面中进行配置，并获取图像请求中的数据。

* 在实施中，此维度从图像请求中的 [`r` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用浏览器中的 JavaScript 变量 `document.referrer` 收集此数据。您可以使用变 [`referrer`](/help/implement/vars/page-vars/referrer.md) 量覆盖来手动设置它。 如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform Launch），则此维度可开箱即用。如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在图像请求中包含 `r` 查询字符串参数。
* 在 Analytics 界面中，必须配置报表包的[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)。无法配置内部 URL 过滤器，可能会包含内部 URL 或阻止出现外部 URL。

## Dimension项

Dimension项包括访客点进您网站的URL。 If a hit does not have any referrer data, it groups under the dimension item `"Typed/Bookmarked"`. 此维度项表示没有推荐人值，例如访客将浏览器地址手动键入地址栏或单击书签。 对于 `"Typed/Bookmarked"` 不适合Analytics的重定向，也会显示维度项。 请参 [阅技术说明](/help/technotes/redirects.md) “用户指南”中的重定向和别名。

### Dimension项包含 `googleusercontent.com`

用户可以查看域中的维项 `googleusercontent.com`目。

* **缓存的页面**:谷歌的蜘蛛会不断地爬网并存储网页副本，以防它们离线。 通过单击“缓存的”链接，这些缓存的页面在大多数搜索结果旁边可用。 当用户单击此链接并视图Google缓存的内容时， `webcache.googleusercontent.com` 这是典型的维度项。
* **翻译页面**：Google 提供了一项强大而便捷的翻译服务。使用此服务查看站点时，服务源自 `translate.googleusercontent.com`。如果用户单击链接返回到原始内容，则显示此维度项。
