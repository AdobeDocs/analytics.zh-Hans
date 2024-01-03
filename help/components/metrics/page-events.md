---
title: 页面事件
description: 触发的链接跟踪操作数量。
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: a7434f72159a575f9ad7bf29644cb17777382df7
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 40%

---

# 页面事件

“页面事件” [量度](overview.md) 显示执行任何链接跟踪调用的次数。 当您想要了解哪些页面具有最吸引人的内容时，此量度很有用。当访客无需导航到新页面即可对页面执行操作时，此量度的度量最有价值。

## 如何计算此量度

此量度计算所有 [链接跟踪调用(`tl()`)](/help/implement/vars/functions/tl-method.md) 在报表包中。 此量度包括所有链接类型，特别是 [自定义链接](../dimensions/custom-link.md)， [下载链接](../dimensions/download-link.md)、和 [退出链接](../dimensions/exit-link.md). 它不包括 [页面查看跟踪调用(`t()`)](/help/implement/vars/functions/t-method.md).

## 与类似指标比较

* **页面事件与 [页面查看次数](page-views.md)**：页面事件计算链接跟踪调用的数量(`tl()`)，并排除页面查看跟踪调用(`t()`)。 页面查看次数则相反；它计算页面查看跟踪调用的数量，不包括链接。
