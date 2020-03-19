---
title: 函数和方法
description: 了解如何在您的实施中使用Adobe提供的功能和方法。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 函数和方法

Adobe提供了多种功能和方法，您可以在实施中使用这些功能和方法。 当您引用这些函数或方法时，它们使用一行代码执行常见任务。

这些代码行中的某些代码行属于以下类别：

* **跟踪调用**:最常见的方法，在许多实现中都至关重要。 包括 [`t()`](t-method.md) 和方 [`tl()`](tl-method.md) 法。
* **AppMeasurement实用程序**:在AppMeasurement的早期版本中，实施必须编写自己的代码才能执行这些任务。 Adobe提供了这些实用程序方法来简化这些常见任务。 AppMeasurement实用程 [`Util.cookieRead()`](util-cookieread.md)序包 [`Util.cookieWrite()`](util-cookiewrite.md)括、和 [`Util.getQueryParam()`](util-getqueryparam.md)。
* **注册功能**:您可以编写自己的函数，并让AppMeasurement在向Adobe发送跟踪调用之前或之后自动执行这些函数。 属于此类别的变量 [`doPlugins()`](doplugins.md)有、 [`registerPreTrackCallback()`](registerpretrackcallback.md)和 [`registerPostTrackCallback()`](registerposttrackcallback.md)。
