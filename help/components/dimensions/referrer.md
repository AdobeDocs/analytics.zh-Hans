---
title: 反向链接
description: 访客在点进到您的网站之前所在的URL。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# 反向链接

“推荐人”维度报告访客点击到达您的站点时所使用的URL。 此维度有助于了解哪些特定URL对您的站点的流量影响最大。 外部URL上必须存在链接，访客必须单击该链接才能显示维值。

>[!IMPORTANT] 必须配置报表包的内 [部URL过滤器](/help/admin/admin/internal-url-filter-admin.md) ，才能使用此维。 未能配置内部URL过滤器可以包含内部URL或阻止显示外部URL。

## 用数据填充此维

此维需要在Analytics界面中进行配置，并在图像请求中进行数据配置。

* 在您的实现中，此维从图像请求中的 [`r` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用浏览器中的JavaScript变量 `document.referrer` 收集此数据。 如果您使用AppMeasurement库（如通过Adobe Experience Platform Launch），此维度将开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在图像请求中包含 `r` 字符串参数。
* 在Analytics界面中，必须配置报表包的内 [部URL过滤器](/help/admin/admin/internal-url-filter-admin.md)。 未能配置内部URL过滤器可以包含内部URL或阻止显示外部URL。

## 维值

维值包括访客点进您网站的URL。 如果点击没有任何推荐人数据，它将在维值下进行分组 `"Typed/Bookmarked"`。 此维度值表示没有推荐人值，如访客将浏览器地址手动键入地址栏或单击书签。
