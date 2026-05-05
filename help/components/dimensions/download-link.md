---
title: 下载链接
description: 下载链接的名称。
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 418e8d467ca29267314e14fba99783d0cb3d05a9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 28%

---

# 下载链接

“下载链接”[维度](overview.md)报告您的网站上实现的下载链接的名称。 当您想要了解有关下载链接的访客行为的更多信息时，此维度很有价值，例如：

* 哪些文件最常从您的网站下载。
* 在特定时间段内是否更频繁地下载某些文件。
* 访客在提供时是否下载不同的文件类型。

## 使用数据填充此维度

此维度根据`pe`查询字符串中的值，从图像请求中的[`pev2`查询字符串](/help/implement/validate/query-parameters.md)收集数据。 `pe`查询字符串确定哪个链接维度接收`pev2`值：

* **[自定义链接](custom-link.md)**： `lnk_o`
* **下载链接** （此页面）： `lnk_d`
* **[退出链接](exit-link.md)**： `lnk_e`

如果未提供`pev2`，则将链接URL (`pev1`)用作维度值。 显式提供链接名称时，最大长度为100字节。 从链接URL派生的值不受此限制约束。

要使用AppMeasurement填充此维度，请发送一个链接类型参数为`"d"`的[`tl()`](/help/implement/vars/functions/tl-method.md)图像请求。 将链接名称参数设置为所需的值：

```js
s.tl(true,"d","Example download link");
```

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。 Adobe 建议您根据报表需求将链接分组为有意义的类别。 如果未提供链接名称，则维度项目将显示为原始URL。 这些原始URL在报表中更难解释，因此请尽可能提供描述性链接名称。
