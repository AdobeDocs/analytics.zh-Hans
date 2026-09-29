---
title: 颜色深度
description: 设备的颜色深度。
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: 'https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%
---
# 颜色深度

“颜色深度”[维度](overview.md)报告设备支持的颜色数量。 确定多少流量来自不支持 1,600 万颜色的设备时，此维度非常有用。 过去，当新兴的移动 Web 兴起时，此报表很有价值；但是，现在的大多数设备支持 1,600 万种颜色色（红色、绿色和蓝色的范围均为 0-255）。<!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## 使用数据填充此维度

颜色深度在客户端从浏览器的`screen.colorDepth`属性中自动收集，Adobe会将该属性通过查询表转换为可读格式。 它可以在任何AppMeasurement或Web SDK（标记）实施中开箱即用 — 没有要设置的变量。 如果您在AppMeasurement或Web SDK之外收集数据（例如通过API），请在每次点击时发送有效位值。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（自动收集） |
| **Web SDK / XDM字段** | 无（自动收集） |
| **查询参数** | [`c`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<colorDepth>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 20字节 |
| **持久性** | 不适用 |

## 维度项目

维度项目包括设备支持的颜色数量。 示例值包括 `"16 million (24-bit)"`、`"16 million (32-bit)"` 和 `"65,536 (16-bit)"`。 如果 AppMeasurement 无法确定颜色深度，则会显示为 `"None"`。

>[!TIP]
>
>24 位和 32 位支持的区别在于：32 位支持 Alpha 通道 (RGBA)，而 24 位则不支持 (RGB)。 有关此概念的更多信息，请参阅 Wikipedia 上的[颜色深度](https://en.wikipedia.org/wiki/Color_depth)。
