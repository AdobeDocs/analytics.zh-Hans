---
title: 原始引用域
description: 访客在点进到您的站点之前访问的第一个引用域。
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# 原始引用域

“原始引用域”维度报告访客点击到您的站点的第一个引用域。 设置后，它包含该访客ID整个生命周期的相同值。 此维度有助于了解最初哪些第三方站点会驱动您的站点的流量。

>[!IMPORTANT]
>
>必须配置报表包的内 [部URL过滤器](/help/admin/admin/internal-url-filter-admin.md) ，才能使用此维。 未配置内部URL过滤器可以包括内部域或阻止显示外部域。

## 用数据填充此维

此维需要在Analytics接口和您的实现中进行配置。

* 在您的实现中，此维从图像请求中的 [`r` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用浏览器中的JavaScript变量 `document.referrer` 收集此数据。 如果您使用AppMeasurement库(如通过Adobe Experience Platform Launch)，则此维度开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在图像请求中包含 `r` 字符串参数。
* 在Analytics界面中，必须配置报表包的内 [部URL过滤器](/help/admin/admin/internal-url-filter-admin.md)。 未配置内部URL过滤器可以包括内部域或阻止显示外部域。

Adobe在访客有生之年仍保留原始引用域。 如果访客随时离开并点击不同域上的链接，则不会记录新值。 如果要查看新值，请参阅引 [用域](referring-domain.md)。

## Dimension项

Dimension项包括访客点击到您的站点的域。 如果点击没有任何推荐人数据（已设置或保留），则它会在维项下进行分组 `"None"`。 此维度项表示没有推荐人值，例如访客将浏览器地址手动键入地址栏或单击书签。

## 将引用域与原始引用域进行比较

引用域可以在访问之间更改。 例如，访客到达您的站 `google.com`点，一周后，到达您的站点 `twitter.com`。 最终，他们在您的网站上进行购买。 如果将引用域用作具有上次触摸归因的维 `twitter.com` ，则获取购买的积分。 如果使用原始引用域作为维，则无论 `google.com` 使用何种归因模型，都将获得购买的信用。

原始引用域在给定访客ID的整个生命周期中都不会更改。
