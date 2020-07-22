---
title: 颜色深度
description: 设备的颜色深度。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# 颜色深度

“颜色深度”维度报告设备支持的颜色数。 此维度可用于确定来自不支持1600万颜色的设备的流量。 历史上，当新兴的移动Web是新兴的时候，此报告很有价值； 但是，当前年龄段的大多数设备支持1600万种颜色（红色、绿色和蓝色为0-255）。 <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## 用数据填充此维

该维引用查找表，将位值转换为更易读的格式。 它从图像请求中 [`c` 的查询](/help/implement/validate/query-parameters.md) 字符串收集数据。 AppMeasurement使用变 `screen.colorDepth` 量填充图像请求查询字符串。 如果您使用AppMeasurement(例如通过Adobe Experience Platform启动)，此维度开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在每次点击时都包含字符串参数，并具有有效位值。 `c`

## 维项

维度项包括设备支持的颜色数。 示例值 `"16 million (24-bit)"`包括 `"16 million (32-bit)"`、和 `"65,536 (16-bit)"`。 如果AppMeasurement无法确定颜色深度，则显示为 `"None"`。

>[!TIP]
>
>24位和32位支持的区别在于32位支持alpha渠道(RGBA)，而24位不支持(RGB)。 请参 [阅Wikipedia上的](https://en.wikipedia.org/wiki/Color_depth) “颜色深度”，以了解有关此概念的更多信息。
