---
title: 比较实施方法
description: 了解每种用于将数据发送到 Adobe Analytics 的方法的优点。
source-git-commit: 2e69321404237213c6929f3fb0c330575d8a90db
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 100%

---

# 比较实施方法

了解每种实施 Adobe Analytics 的方法的比较情况。您可以使用此表来帮助您的组织确定用于向 Adobe 发送数据的最理想方法。

|  | AppMeasurement | Adobe Analytics 扩展 | Web SDK | Web SDK 扩展 |
| --- | --- | --- | --- | --- |
| 实施要求 | 在每个页面上参考 `AppMeasurement.js`，定义变量，使用 `s.t()` 发送数据 | 在每个页面上参考标记加载器，使用数据收集 UI 定义变量并将数据发送到 Adobe | 在每个页面上参考 `Alloy.js`，使用 `alloy("sendEvent",{})` 发送包含所需数据的 JSON 对象 | 在每个页面上参考标记加载器，使用数据收集 UI 建立 JSON 对象以发送数据 |
| 数据目标 | 直接发送到 Adobe Analytics | 直接发送到 Adobe Analytics | 发送到 Adobe Experience Platform Edge，后者会将数据转发到 Adobe Analytics | 发送到 Adobe Experience Platform Edge，后者会将数据转发到 Adobe Analytics |
| 难以进行实施调整 | 每次实施更改都需要访问网站代码 | 更改网站代码一次以安装加载器标记；可在数据收集 UI 中进行所有进一步的实施更新 | 每次实施更改都需要访问网站代码 | 更改网站代码一次以安装加载器标记；可在数据收集 UI 中进行所有进一步的实施更新 |
| 如何处理 A4T | A4T 调用包含在已发送到 Adobe 的点击中 | A4T 调用包含在已发送到 Adobe 的点击中 | A4T 调用作为单独的点击发送 | A4T 调用作为单独的点击发送 |
| 上下文数据 | 使用 `s.contextData`。 | 在自定义代码块中使用 `s.contextData` | 作为 `a.x.*` 上下文数据变量自动发送所有未映射的字段。 | 作为 `a.x.*` 上下文数据变量自动发送所有未映射的字段。 |

{style="table-layout:auto"}
