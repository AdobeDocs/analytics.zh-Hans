---
title: 浏览器高度——分时段
description: 浏览器窗口的高度（以像素为单位）。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# 浏览器高度

“浏览器高度——分时段”尺寸显示浏览器窗口的高度，按100像素的组进行分类。 当您想要了解网站上的“折叠”对访客的位置时，此维度很有用。 了解折叠的位置可让您优化内容以供查看。

此尺寸与屏幕高度不同。 浏览器高度是可查看的浏览器空间中的像素数，而屏幕高度是整个显示器的高度（以像素为单位）。 如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（大多数浏览器上的F12），然后复制并粘贴以下代码到控制台中：

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

浏览器高度始终小于或等于屏幕高度，因为浏览器高度不包括浏览器导航或边框。

## 用数据填充此维

此维从图像请求中的 [`bh` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用浏览器中的JavaScript变量 `window.innerHeight` 收集此数据。 如果您使用AppMeasurement库(如通过Adobe Experience Platform启动)，则此维度开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在每次访问的第一次点击时包含 `bh` 字符串参数。

Adobe会持续显示浏览器高度以供访问。 如果在访问中调整了浏览器高度，则不记录调整。

## 维项

维度项目包括所有收集的浏览器高度，分为100像素的组。 例如，如果点击的浏览器高度 `720`为，则它将在维项中分组 `700 to 799`。
