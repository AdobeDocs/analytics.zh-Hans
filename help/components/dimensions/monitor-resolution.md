---
title: 监视器分辨率
description: 访客的监视器分辨率（以像素为单位）。
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
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
source-wordcount: '289'
ht-degree: 51%
---
# 监视器分辨率

“监视器分辨率”[维度](overview.md)以像素为单位显示活动显示器的高度和宽度。 当您想要了解访客在您的网站上“折叠”窗口的位置，或访客的浏览器窗口宽度时，此维度很有用。 了解折叠的位置可让您优化内容以便于查看。

此维度与浏览器[高度](browser-height.md)和[宽度](browser-width.md)不同。 浏览器高度/宽度是指可查看的浏览器空间中的像素数，而监视器分辨率是指整个监视器的像素数。 如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（在大多数浏览器上是按 F12），然后将以下代码复制并粘贴到控制台中：

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

浏览器尺寸始终小于监视器分辨率，因为浏览器尺寸不包括浏览器导航或边框。

## 使用数据填充此维度

在客户端从浏览器的`screen.width`和`screen.height`属性中自动收集监视器分辨率。 它可以在任何AppMeasurement或Web SDK（标记）实施中开箱即用 — 没有要设置的变量。 如果您在AppMeasurement或Web SDK之外收集数据（例如通过API），请在图像请求中发送该值。 如果缺少此数据或数据收集库无法收集监视器分辨率，则该数据将列在[!UICONTROL `Not Specified`]下。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（自动收集） |
| **Web SDK / XDM字段** | 无（自动收集） |
| **查询参数** | [`s`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<resolution>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 20字节 |
| **持久性** | 不适用 |

## 维度项目

维度项包括所有收集的监视器分辨率。 示例值包括 `1920 x 1080`、`1366 x 768` 和 `1280 x 720`。
