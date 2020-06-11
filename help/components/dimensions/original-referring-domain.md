---
title: 原始引用域
description: 访客在点进到您的站点之前访问的第一个引用域。
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---


# 原始引用域

“原始引用域”维度报告访客点击到您的站点的第一个引用域。 设置后，它包含该访客ID整个生命周期的相同值。 此维度有助于了解最初哪些第三方站点会驱动您的站点的流量。

## 用数据填充此维

此维度需要在Analytics界面和您的实施中进行配置。

* 在您的实现中，此维从图像请求中的 [`r` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用浏览器中的JavaScript变量 `document.referrer` 收集此数据。 如果您使用AppMeasurement库（如通过Adobe Experience Platform Launch），此维度将开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在图像请求中包含 `r` 字符串参数。
* 在Analytics界面中，必须配置报表包的内 [部URL过滤器](/help/admin/admin/internal-url-filter-admin.md)。 未配置内部URL过滤器可以包括内部域或阻止显示外部域。

Adobe在访客的一生中保留原始引用域。 如果访客随时离开并点击不同域上的链接，则不会记录新值。 如果要查看新值，请参阅引 [用域](referring-domain.md)。

## 维值

维值包括访客点进您的站点的域。 如果点击没有任何推荐人数据（设置或保留），则它将组合在维值下 `"None"`。 此维度值表示没有推荐人值，如访客将浏览器地址手动键入地址栏或单击书签。
