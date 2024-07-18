---
title: 浏览器宽度 - 分段统计
description: 浏览器窗口的宽度（以像素为单位）。
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
source-git-commit: 2601b0e5c3fa78237ce693801b8dd8c95b853b81
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 81%

---

# 浏览器宽度

“浏览器宽度 — 分段统计”维度[维度](overview.md)显示浏览器窗口的宽度，并将其分类为预定义的组。 当您想要了解访客查看内容的范围时，此维度非常有用。了解您的内容通常在中查看的宽度可以让您优化该内容。

此维度与屏幕宽度不同。 浏览器宽度是指浏览器可见空间内的像素数，而屏幕宽度是指整个显示器的宽度（以像素为单位）。如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（在大多数浏览器上是按 F12），然后将以下代码复制并粘贴到控制台中：

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

浏览器宽度始终小于或等于屏幕宽度，因为浏览器宽度不包括滚动条或边框。

## 使用数据填充此维度

此维度从图像请求中的 [`bw` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用浏览器中的 JavaScript 变量 `window.innerWidth` 收集此数据。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在每个访问的首次点击时包含 `bw` 查询字符串参数。

Adobe 会保留访问的浏览器宽度。如果在访问过程中调整了浏览器宽度，则不会记录调整的情况。

## 维度项目

Dimension项目包括所有收集的浏览器宽度，它们分类为预定义组。 例如，如果点击的浏览器宽度为 `1280`，则会将其分组到维度项目 `1200 to 1299`。
