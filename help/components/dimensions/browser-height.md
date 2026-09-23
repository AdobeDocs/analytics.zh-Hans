---
title: 浏览器高度 - 分段统计
description: 以像素为单位的浏览器窗口的高度。
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 40%
---
# 浏览器高度

“浏览器高度 — 分段统计”维度[维度](overview.md)显示浏览器窗口的高度，并将其归类到预定义的组中。 当您想要了解网站上的“折”对访客的位置时，此维度很有用。 了解折的位置可让您优化内容以便于查看。

此维度与屏幕高度不同。 浏览器高度是可查看的浏览器空间中的像素数，而屏幕高度是以像素为单位的整个显示器的高度。 如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（在大多数浏览器上是按 F12），然后将以下代码复制并粘贴到控制台中：

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

浏览器高度通常小于或等于屏幕高度，因为浏览器高度不包括浏览器导航或边框。

>[!NOTE]
>
>Data Warehouse还提供“[!UICONTROL 浏览器高度 — 粒度]”维度，该维度报告准确的像素高度，而不是将值分组到预定义的桶。

## 使用数据填充此维度

从浏览器的`window.innerHeight`属性在客户端自动收集浏览器高度。 它可以在任何AppMeasurement或Web SDK（标记）实施中开箱即用 — 没有要设置的变量。 如果您在AppMeasurement或Web SDK之外收集数据（例如通过API），请在每次访问首次点击时发送值。 如果在访问中调整了浏览器高度，则不会记录该调整。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（自动收集） |
| **Web SDK / XDM字段** | 无（自动收集） |
| **查询参数** | [`bh`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<browserHeight>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **值范围** | 0-65,535 |
| **持久性** | 访问 |

## 维度项目

Dimension项目包括所有收集的浏览器高度，它们被分类为预定义的组。 例如，如果点击的浏览器高度为 `720`，则会将其分组到维度项目 `700 to 799`。
