---
title: 浏览器宽度——分时段
description: 浏览器窗口的宽度（以像素为单位）。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# 浏览器宽度

“浏览器宽度——分时段”尺寸显示浏览器窗口的宽度，按100像素的组进行分类。 当您想要了解访客查看内容的范围时，此维度很有用。 了解内容的查看范围通常允许您优化内容以供查看。

此尺寸不同于屏幕宽度。 浏览器宽度是可查看浏览器空间中的像素数，而屏幕宽度是整个显示器的宽度（以像素为单位）。 如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（大多数浏览器上的F12），然后复制并粘贴以下代码到控制台中：

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

浏览器宽度始终小于或等于屏幕宽度，因为浏览器宽度不包括滚动条或边框。

## 用数据填充此维

此维从图像请求中的 [`bw` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用浏览器中的JavaScript变量 `window.innerWidth` 收集此数据。 如果您使用AppMeasurement库(如通过Adobe Experience Platform启动)，则此维度开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在每次访问的第一次点击时包含 `bw` 字符串参数。

Adobe会持续显示浏览器宽度进行访问。 如果在访问中调整了浏览器宽度，则不记录调整。

## 维项

尺寸项包括所有收集的浏览器宽度，分为100像素的组。 例如，如果点击的浏览器宽度 `1280`为，则它将在维度项中分组 `1200 to 1299`。
