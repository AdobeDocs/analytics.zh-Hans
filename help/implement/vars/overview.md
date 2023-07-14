---
title: 变量、函数、方法及插件概述
description: 了解您可以在向 Adobe 发送的数据中包含哪些变量以改进报告。
keywords: appmeasurement,变量,变量,配置,页面,实施
feature: Variables
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
source-git-commit: 1516a1353c1b0a3b7365c3e3f10ce74ae1255696
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 70%

---

# 变量、函数、方法及插件概述

Analytics 提供了多个变量来收集 Analytics 数据。此部分中的变量可分为以下几类：

* **页面变量**：通常在报告中直接使用的值。常用页面变量包括 `props`、`eVars` 和 `events`。
* **配置变量**：可帮助确保将正确数据发送到 Adobe 的设置值。常用配置变量包括 `trackingServerSecure`、`charSet` 和 `linkTrackVars`。配置变量通常不会填充维度项目。
* **函数和方法**：在被引用时可执行特定任务的代码段。常用函数包括 `t()`、`tl()` 和 `clearVars()`。

## 变量和实施方法

Adobe 提供了多种实施 Adobe Analytics 的方法。每个页面都提供一个部分，介绍如何使用Web SDK、使用Adobe Analytics扩展和使用JavaScriptAppMeasurement来实施变量。

以下是一段关于在 Adobe Analytics 中配置变量的视频：

>[!VIDEO](https://video.tv.adobe.com/v/28755/?quality=12)

## 操作顺序

在向 Adobe 发送数据时，由 Adobe Analytics 发布的 AppMeasurement 库将按特定顺序依次执行。如果您不按顺序执行任务，则数据可能不完整。

1. 如果您的网站使用数据层，请确保首先填充所有适用变量。例如，您填充 `adobeDataLayer.page.title` 带有页面标题。 有关更多信息，请参阅[数据层](../prepare/data-layer.md)。
2. 使用数据层填充 Analytics 变量。<br/>如果您使用Adobe Experience Platform中的标记，则可通过在标记与标记之间使用数据元素来完成此任务。 使用数据层中的值填充数据元素。 例如，数据元素 `Page Title` 从数据层变量中获取值 `adobeDataLayer.page.title`. <br/>然后，您可以使用数据元素填充Analytics变量。 例如 `eVar4` 从数据元素中获取值 `Page Title`. <br/>有关更多信息，请参阅 [数据元素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=zh-Hans)， [将数据层对象映射到数据元素](../launch/layer-to-elements.md)、和 [将标记数据元素映射到Analytics变量](../launch/elements-to-variable.md)
3. 最后，调用跟踪函数。 大多数 AppMeasurement 库都使用 `t()` 方法，但某些 Mobile SDK 使用 `track()`。调用跟踪函数时，在 Analytics 对象中定义的所有受支持变量都将以图像请求的形式发送到 Adobe。

## 非法字符

决不允许在 JavaScript 变量中使用以下字符和字符串。

* 制表符 (`0x09`)
* 回车符 (`0x0D`)
* 换行符 (`0x0A`)
* HTML 标记（例如 `<b></b>` 或 `&#153`）

某些变量还有其他限制或语法要求。例如，[`products`](page-vars/products.md) 变量保留分号和逗号，以分隔不同的产品和类别。
