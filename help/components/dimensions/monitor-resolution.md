---
title: 监视器分辨率
description: 访客的监视器分辨率（以像素为单位）。
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 82%

---

# 监视器分辨率

“监视器分辨率”[维度](overview.md)以像素为单位显示活动显示器的高度和宽度。 当您想要了解访客在您的网站上“折叠”窗口的位置，或访客的浏览器窗口宽度时，此维度很有用。 了解折叠的位置可让您优化内容以便于查看。

此维度与浏览器[高度](browser-height.md)和[宽度](browser-width.md)不同。 浏览器高度/宽度是指可查看的浏览器空间中的像素数，而监视器分辨率是指整个监视器的像素数。 如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（在大多数浏览器上是按 F12），然后将以下代码复制并粘贴到控制台中：

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

浏览器尺寸始终小于监视器分辨率，因为浏览器尺寸不包括浏览器导航或边框。

## 使用数据填充此维度

此维度从图像请求中的 [`s` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。 AppMeasurement 使用浏览器中的 JavaScript 变量 `screen.width` 和 `screen.height` 收集此数据。 如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。

如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在图像请求中包含 `s` 查询字符串参数。 如果`s`查询字符串缺失或数据收集库无法收集监视器分辨率，则该数据将列在[!UICONTROL `Not Specified`]下。

## 维度项目

维度项目包括所有收集的监视器分辨率。 示例值包括 `1920 x 1080`、`1366 x 768` 和 `1280 x 720`。
