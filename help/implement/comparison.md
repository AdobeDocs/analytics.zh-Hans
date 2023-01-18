---
title: 比较实施方法
description: 了解将数据发送到Adobe Analytics的每种方法的优势。
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# 比较实施方法

查看实施Adobe Analytics的每种方法之间的对比情况。 您可以使用此表帮助贵组织确定将数据发送到Adobe的最理想方式。

|  | AppMeasurement | Adobe Analytics 扩展 | Web SDK | Web SDK扩展 |
| --- | --- | --- | --- | --- |
| 实施要求 | 参考 `AppMeasurement.js` 在每个页面上，定义变量，使用 `s.t()` | 在每个页面上引用标记加载器，使用数据收集UI定义变量并将数据发送到Adobe | 参考 `Alloy.js` 在每个页面上，使用 `alloy("sendEvent",{})` 发送包含所需数据的JSON对象 | 在每个页面上引用标记加载器，使用数据收集UI建立JSON对象以发送数据 |
| 数据目标 | 直接发送到Adobe Analytics | 直接发送到Adobe Analytics | 发送到Adobe Experience Platform Edge，后者会将数据转发到Adobe Analytics | 发送到Adobe Experience Platform Edge，后者会将数据转发到Adobe Analytics |
| 实施调整困难 | 需要访问每个实施更改的网站代码 | 只需更改网站代码一次即可安装加载器标记；所有进一步的实施更新都可以在数据收集UI中进行 | 需要访问每个实施更改的网站代码 | 只需更改网站代码一次即可安装加载器标记；所有进一步的实施更新都可以在数据收集UI中进行 |
| 如何处理A4T | A4T调用包含在发送到Adobe的点击中 | A4T调用包含在发送到Adobe的点击中 | A4T调用将作为单独的点击发送 | A4T调用将作为单独的点击发送 |
| 如何处理反向链接 |