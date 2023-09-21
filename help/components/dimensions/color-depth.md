---
title: 颜色深度
description: 设备的颜色深度。
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 94%

---

# 颜色深度

“颜色深度” [维度](overview.md) 报告设备支持的颜色数量。 确定多少流量来自不支持 1,600 万颜色的设备时，此维度非常有用。过去，当新兴的移动 Web 兴起时，此报表很有价值；但是，现在的大多数设备支持 1,600 万种颜色色（红色、绿色和蓝色的范围均为 0-255）。<!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## 使用数据填充此维度

此维度引用查找表，将位值转换为更易于读取的格式。它会从图像请求中的 [`c` 查询字符串](/help/implement/validate/query-parameters.md)收集数据。AppMeasurement 会使用 `screen.colorDepth` 变量填充图像请求查询字符串。如果您使用 AppMeasurement（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在每次点击时包含 `c` 查询字符串参数，并具有有效位值。

## 维度项目

维度项目包括设备支持的颜色数量。示例值包括 `"16 million (24-bit)"`、`"16 million (32-bit)"` 和 `"65,536 (16-bit)"`。如果 AppMeasurement 无法确定颜色深度，则会显示为 `"None"`。

>[!TIP]
>
>24 位和 32 位支持的区别在于：32 位支持 Alpha 通道 (RGBA)，而 24 位则不支持 (RGB)。有关此概念的更多信息，请参阅 Wikipedia 上的[颜色深度](https://en.wikipedia.org/wiki/Color_depth)。
