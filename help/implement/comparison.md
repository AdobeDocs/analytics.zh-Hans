---
title: 比较实施方法
description: 了解每种用于将数据发送到 Adobe Analytics 的方法的优点。
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# 比较实施方法

了解每种实施 Adobe Analytics 的方法的比较情况。您可以使用此表来帮助您的组织确定用于向 Adobe 发送数据的最理想方法。

|  | AppMeasurement | Adobe Analytics 扩展 | Web SDK | Web SDK 扩展 |
| --- | --- | --- | --- | --- |
| 实施要求 | 在每个页面上参考 `AppMeasurement.js`，定义变量，使用 `s.t()` 发送数据 | 在每个页面上参考标记加载器，使用数据收集 UI 定义变量并将数据发送到 Adobe | 在每个页面上参考 `Alloy.js`，使用 `alloy("sendEvent",{})` 发送包含所需数据的 JSON 对象 | 在每个页面上参考标记加载器，使用数据收集 UI 建立 JSON 对象以发送数据 |
| 数据目标 | 直接发送到 Adobe Analytics | 直接发送到 Adobe Analytics | 发送到 Adobe Experience Platform Edge，后者会将数据转发到 Adobe Analytics | 发送到 Adobe Experience Platform Edge，后者会将数据转发到 Adobe Analytics |
| 难以进行实施调整 | 每次实施更改都需要访问网站代码 | 网站代码只需更改一次即可安装加载器标记；所有进一步的实施更新都可以在数据收集 UI 中进行 | 每次实施更改都需要访问网站代码 | 网站代码只需更改一次即可安装加载器标记；所有进一步的实施更新都可以在数据收集 UI 中进行 |
| 如何处理 A4T | A4T 调用包含在已发送到 Adobe 的点击中 | A4T 调用包含在已发送到 Adobe 的点击中 | A4T 调用作为单独的点击发送 | A4T 调用作为单独的点击发送 |
| 如何处理反向链接 |