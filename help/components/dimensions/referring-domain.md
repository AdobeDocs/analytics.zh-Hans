---
title: 引荐域名
description: 访客在点击到您的网站之前所处的总域。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 1%

---


# 引荐域名

“引用域”维度报告访客点击哪些域以访问您的站点。 此维度有助于了解哪些第三方站点对您的站点的流量最大。 外部站点上必须存在链接，访客必须单击该链接才能显示维项目。

>[!IMPORTANT]
>
>必须配置报表包的内 [部URL过滤器](/help/admin/admin/internal-url-filter-admin.md) ，才能使用此维。 未配置内部URL过滤器可以包括内部域或阻止显示外部域。

## 用数据填充此维

此维需要在Analytics接口中配置，并在图像请求中配置数据。

* 在您的实现中，此维从图像请求中的 [`r` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用浏览器中的JavaScript变量 `document.referrer` 收集此数据。 如果您使用AppMeasurement库(如通过Adobe Experience Platform启动)，则此维度开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在图像请求中包含 `r` 字符串参数。
* 在Analytics界面中，必须配置报表包的内 [部URL过滤器](/help/admin/admin/internal-url-filter-admin.md)。 未配置内部URL过滤器可以包括内部域或阻止显示外部域。

Adobe继续为访问引用域。 如果访客离开并在单次访问中点击不同域上的链接，则新值会更新并持续到剩余的访问时间。 如果只想查看原始值，请参阅原始 [引用域](original-referring-domain.md)。

## 维项

维项目包括访客点进您站点的域。 如果点击没有任何推荐人数据（已设置或保留），则它会在维项下进行分组 `"Typed/Bookmarked"`。 此维度项表示没有推荐人值，例如访客将浏览器地址手动键入地址栏或单击书签。
