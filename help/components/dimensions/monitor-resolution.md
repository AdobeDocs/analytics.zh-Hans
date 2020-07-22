---
title: 显示器分辨率
description: 访客显示器的分辨率（以像素为单位）。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---


# 显示器分辨率

“监视器分辨率”尺寸以像素为单位显示活动显示的高度和宽度。 当您想要了解“折叠”在您的站点对访客的位置，或访客可以打开浏览器窗口的范围时，此维度很有用。 了解折叠的位置可让您优化内容以供查看。

此尺寸与浏览器高度和宽度不同。 浏览器高度／宽度是可查看的浏览器空间中的像素数，而显示器分辨率是整个显示器的像素数。 如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（大多数浏览器上的F12），然后复制并粘贴以下代码到控制台中：

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

浏览器尺寸始终小于显示器分辨率，因为浏览器尺寸不包括浏览器导航或边框。

## 用数据填充此维

此维从图像请求中的 [`s` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用JavaScript变量在浏览器中 `screen.width` 收 `screen.height` 集此数据。 如果您使用AppMeasurement库(如通过Adobe Experience Platform启动)，则此维度开箱即用。 如果您在AppMeasurement之外使用查询收集方法（如通过API），请确保在图像请求中包含 `s` 字符串参数。

## 维项

维度项目包括所有收集的监视器分辨率。 示例值 `1920 x 1080`包括 `1366 x 768`、和 `1280 x 720`。
