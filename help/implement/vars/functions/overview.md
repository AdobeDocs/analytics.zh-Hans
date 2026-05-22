---
title: 函数和方法
description: 了解如何在您的实施中使用 Adobe 提供的函数和方法。
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/dKPvTPeRa7-SIFyIDU-7Mlob-3jsrfvhWmKeAveHGEc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 100%

---

# 函数和方法

Adobe 提供了多个可在在实施中使用的函数和方法。 当您引用这些函数或方法时，它们只需一行代码即可执行常见任务。

其中某些单行代码属于以下类别：

* **跟踪调用**：最常用的方法，在许多实施中都至关重要。 包括 [`t()`](t-method.md) 方法和 [`tl()`](tl-method.md) 方法。
* **AppMeasurement 实用程序**：在 AppMeasurement 的先前版本中，实施必须编写自己的代码才能执行这些任务。 Adobe 提供这些实用程序方法来简化常见任务。 AppMeasurement 实用程序包括 [`Util.cookieRead()`](util-cookieread.md)、[`Util.cookieWrite()`](util-cookiewrite.md) 和 [`Util.getQueryParam()`](util-getqueryparam.md)。
* **注册函数**：您可以编写自己的函数，并让 AppMeasurement 在向 Adobe 发送跟踪调用之前或之后自动执行这些函数。 属于这一类别的变量有 [`doPlugins()`](doplugins.md)、[`registerPreTrackCallback()`](registerpretrackcallback.md) 和 [`registerPostTrackCallback()`](registerposttrackcallback.md)。
