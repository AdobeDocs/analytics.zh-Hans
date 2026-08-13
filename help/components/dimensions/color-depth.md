---
title: 颜色深度
description: 设备的颜色深度。
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 94%

---

# 颜色深度

“颜色深度”[维度](overview.md)报告设备支持的颜色数量。 确定多少流量来自不支持 1,600 万颜色的设备时，此维度非常有用。 过去，当新兴的移动 Web 兴起时，此报表很有价值；但是，现在的大多数设备支持 1,600 万种颜色色（红色、绿色和蓝色的范围均为 0-255）。<!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## 使用数据填充此维度

此维度引用查找表，将位值转换为更易于读取的格式。 它会从图像请求中的 [`c` 查询字符串](/help/implement/validate/query-parameters.md)收集数据。 AppMeasurement 会使用 `screen.colorDepth` 变量填充图像请求查询字符串。 如果您使用 AppMeasurement（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。 如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在每次点击时包含 `c` 查询字符串参数，并具有有效位值。

## 维度项目

维度项目包括设备支持的颜色数量。 示例值包括 `"16 million (24-bit)"`、`"16 million (32-bit)"` 和 `"65,536 (16-bit)"`。 如果 AppMeasurement 无法确定颜色深度，则会显示为 `"None"`。

>[!TIP]
>
>24 位和 32 位支持的区别在于：32 位支持 Alpha 通道 (RGBA)，而 24 位则不支持 (RGB)。 有关此概念的更多信息，请参阅 Wikipedia 上的[颜色深度](https://en.wikipedia.org/wiki/Color_depth)。
