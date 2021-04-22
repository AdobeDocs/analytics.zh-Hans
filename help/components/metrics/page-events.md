---
title: 页面事件
description: 触发的链接跟踪操作数量。
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '143'
ht-degree: 100%

---

# 页面事件

“页面事件”量度显示进行的任何链接跟踪调用的次数。当您想要了解哪些页面具有最吸引人的内容时，此量度很有用。当访客无需导航到新页面即可对页面执行操作时，此量度的度量最有价值。

## 如何计算此量度

此量度计数报表包中所有链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md))。包括所有链接类型（自定义链接、下载链接和退出链接）。它不包括页面查看跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md))。

## 与类似量度比较

* **页面事件与[页面查看次数](page-views.md)**：页面事件计算链接跟踪调用 (`tl()`) 的数量，不包括页面查看跟踪调用 (`t()`)。页面查看次数则相反；它计算页面查看跟踪调用的数量，不包括链接。
