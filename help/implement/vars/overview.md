---
title: 变量、函数、方法和插件概述
description: 了解您可以在发送到Adobe的数据中包含哪些变量以改进报告。
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# 变量、函数、方法和插件概述

Analytics 提供了多个变量来收集 Analytics 数据。此部分中的变量分为几个部分：

* **页面变量** ，是通常在报告中直接使用的值。 常见页面变 `props`量包括 `eVars`、和 `events`。
* **配置变量** ，是帮助确保正确数据到达Adobe的设置值。 常见配置变 `trackingServerSecure`量包括 `charSet`、和 `linkTrackVars`。 配置变量通常不填充维值。
* **函数和方法** ，是在被引用时执行特定任务的一段代码。 常见功 `t()`能包括 `tl()`、和 `clearVars()`。

## 变量和实现方法

Adobe提供多种实施Adobe Analytics的方法。 每个页面都提供一个部分，说明如何使用Launch和AppMeasurement for JavaScript实现变量。

## 操作顺序

Adobe Analytics发布的AppMeasurement库在向Adobe发送数据时按照特定顺序排列。 如果您按顺序执行这些任务，则数据可能不完整。

1. 如果站点使用数据层，请确保首先填充所有适用的变量。 有关更 [多信息](../prepare/data-layer.md) ，请参阅数据层。
2. 使用数据层填充Analytics变量。 如果您使用Launch，则通过使用数据元素然后将数据元素分配到变量，可轻松完成此任务。 请参 [阅启动用户指南](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html) 中的数据元素。
3. 调用跟踪函数。 大多数AppMeasurement库都使 `t()` 用该函数，但某些移动SDK使用该函数 `track()`。 调用跟踪函数时，Analytics对象中定义的所有受支持变量将以图像请求的形式发送到Adobe。

## 非法字符

JavaScript变量中不允许使用以下字符和字符串。

* 制表符 (`0x09`)
* 回车(`0x0D`)
* 换行符 (`0x0A`)
* HTML tags (e.g. `<b></b>` or `&#153`)

某些变量有其他限制或语法要求。 例如，该变量 `products` 保留分号和逗号，以分隔不同的产品和类别。
