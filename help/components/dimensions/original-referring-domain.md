---
title: 原始反向链接域
description: 访客在点击进入您的网站之前所处的首个反向链接域。
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 95%

---

# 原始反向链接域

“原始反向链接域”[维度](overview.md)报告访客点击进入您的网站的第一个反向链接域。 设置后，它在该访客 ID 的整个生命周期内包含相同的值。此维度有助于了解哪些第三方网站最初为您的网站带来了流量。

>[!IMPORTANT]
>
>必须配置报表包的[内部 URL 过滤器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)，才能使用此维度。无法配置内部 URL 过滤器，可能会包含内部域或阻止出现外部域。

## 使用数据填充此维度

需要在 Analytics 界面和您的实施中配置此维度。

* 在实施中，此维度从图像请求中的 [`r` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用浏览器中的 JavaScript 变量 `document.referrer` 收集此数据。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在图像请求中包含 `r` 查询字符串参数。
* 在 Analytics 界面中，必须配置报表包的[内部 URL 过滤器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。无法配置内部 URL 过滤器，可能会包含内部域或阻止出现外部域。

Adobe 会在访客的生命周期内保留原始反向链接域。如果访客随时离开并点击不同域上的链接，则不会记录新值。如果要查看新值，请参阅[反向链接域](referring-domain.md)。

## 维度项目

维度项目包括访客点击进入您的网站的域。如果点击没有任何反向链接数据（设置或保留），则它会分组到维度项目 `"None"` 下。此维度项目表示不存在反向链接值，例如，如果访客在地址栏中手动键入浏览器地址，或单击书签。

## 比较反向链接域与原始反向链接域

在不同访问之间，反向链接域可能会发生改变。例如，访客通过 `google.com` 到达您的网站，一周后，又通过 `twitter.com` 到达您的网站。最终，他们在您的网站上进行购买。如果将“反向链接域”用作维度并采用最近联系归因，则 `twitter.com` 会获得该购买的点数。如果将“原始反向链接域”用作维度，则无论采用何种归因模型，`google.com` 都会获得该购买的点数。

在给定访客 ID 的整个生命周期内，原始反向链接域从不会发生改变。
