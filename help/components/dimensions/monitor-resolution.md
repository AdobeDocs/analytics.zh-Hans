---
title: 监视器分辨率
description: 访客的监视器分辨率（以像素为单位）。
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 93%

---

# 监视器分辨率

“显示器分辨率” [维度](overview.md) 显示活动显示器的高度和宽度（以像素为单位）。 当您想要了解访客在您的网站上“折叠”窗口的位置，或访客的浏览器窗口宽度时，此维度很有用。了解折叠的位置可让您优化内容以便于查看。

此维度与浏览器高度和宽度不同。浏览器高度/宽度是指可查看的浏览器空间中的像素数，而监视器分辨率是指整个监视器的像素数。如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（在大多数浏览器上是按 F12），然后将以下代码复制并粘贴到控制台中：

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

浏览器尺寸始终小于监视器分辨率，因为浏览器尺寸不包括浏览器导航或边框。

## 使用数据填充此维度

此维度从图像请求中的 [`s` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用浏览器中的 JavaScript 变量 `screen.width` 和 `screen.height` 收集此数据。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在图像请求中包含 `s` 查询字符串参数。

## 维度项目

维度项目包括所有收集的监视器分辨率。示例值包括 `1920 x 1080`、`1366 x 768` 和 `1280 x 720`。
