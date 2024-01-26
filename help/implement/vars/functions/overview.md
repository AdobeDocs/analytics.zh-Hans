---
title: 函数和方法
description: 了解如何在您的实施中使用 Adobe 提供的函数和方法。
feature: Variables
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 100%

---

# 函数和方法

Adobe 提供了多个可在在实施中使用的函数和方法。当您引用这些函数或方法时，它们只需一行代码即可执行常见任务。

其中某些单行代码属于以下类别：

* **跟踪调用**：最常用的方法，在许多实施中都至关重要。包括 [`t()`](t-method.md) 方法和 [`tl()`](tl-method.md) 方法。
* **AppMeasurement 实用程序**：在 AppMeasurement 的先前版本中，实施必须编写自己的代码才能执行这些任务。Adobe 提供这些实用程序方法来简化常见任务。AppMeasurement 实用程序包括 [`Util.cookieRead()`](util-cookieread.md)、[`Util.cookieWrite()`](util-cookiewrite.md) 和 [`Util.getQueryParam()`](util-getqueryparam.md)。
* **注册函数**：您可以编写自己的函数，并让 AppMeasurement 在向 Adobe 发送跟踪调用之前或之后自动执行这些函数。属于这一类别的变量有 [`doPlugins()`](doplugins.md)、[`registerPreTrackCallback()`](registerpretrackcallback.md) 和 [`registerPostTrackCallback()`](registerposttrackcallback.md)。
