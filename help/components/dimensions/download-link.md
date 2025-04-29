---
title: 下载链接
description: 下载链接的名称。
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 74%

---

# 下载链接

“下载链接”[维度](overview.md)报告您的网站上实现的下载链接的名称。 当您想要了解有关下载链接的访客行为的更多信息时，此维度很有价值，例如：

* 确定您网站中下载最频繁的文件。
* 了解某些文件在特定时段内下载的次数是否更多。
* 验证是否已提供访客下载的不同文件类型。

## 使用数据填充此维度

此维度从图像请求中的 [`pev2` 查询字符串](/help/implement/validate/query-parameters.md)为还具有值为 `lnk_d` 的 `pe` 查询字符串的点击收集数据。如果`pe`查询字符串在点击中具有不同的值，则此维度不会收集数据。 此维度的最大长度为100字节。

如果要使用 AppMeasurement 将数据发送到此维度，请发送一个 [`tl()`](/help/implement/vars/functions/tl-method.md) 图像请求，其链接类型参数为 `"d"`。使用所需的值填充链接名称参数：

```js
s.tl(true,"d","Example download link");
```

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。Adobe 建议您根据报表需求将链接分组为有意义的类别。
