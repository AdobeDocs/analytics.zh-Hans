---
description: 这两个量度专指浏览器窗口中数据的水平/垂直距离。如需具体信息，请参阅浏览器
seo-description: 这两个量度专指浏览器窗口中数据的水平/垂直距离。如需具体信息，请参阅浏览器
seo-title: 浏览器宽度/高度
solution: Analytics
title: 浏览器宽度/高度
topic: 量度
uuid: 1c0d3ea9-e001-4152-9bfc-8fe6406 bc755
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 浏览器宽度/高度

这两个量度专指浏览器窗口中数据的水平/垂直距离。如需具体信息，请参阅浏览器

Adobe Analytics 仅使用来自某访问第一次点击的浏览器高度和宽度。其余的点击不会得到同一访问的属性。The browser width/height dimensions capture similar but distinct values when compared with [mobile screen size](../../../components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150).

例如，当您对浏览器宽度或高度按移动设备分辨率进行划分时，您需要注意到以下不同之处：

* 移动设备分辨率是指与该设备相关联的物理值。例如，在“移动设备分辨率”下方，Galaxy S8 会显示为 2,960 x 1,440。移动设备分辨率是在识别出设备后从第三方服务中检索出来的。
* 相比之下，在“浏览器高度和宽度”值下方，您看到的 CSS（逻辑）值是 740 x 360。浏览器高度和宽度值依赖于 Javascript/CSS 数据。
* 有关上述内容的简要讨论，请参阅[此主题](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio)。

