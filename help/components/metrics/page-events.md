---
title: 页面事件
description: 触发的链接跟踪操作数。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# 页面事件

“页面事件”度量显示进行任何链接跟踪调用的次数。 当您想要了解哪些页面具有最吸引人的内容时，此指标非常有用。 当访客无需导航到新页面即可对页面执行操作时，此度量的衡量最有价值。

## 如何计算此度量

此度量计算报表包中的所[`tl()`](/help/implement/vars/functions/tl-method.md)有链接跟踪调用()。 包括所有链接类型（自定义链接、下载链接和退出链接）。 它不包括页面视图跟踪调用([`t()`](/help/implement/vars/functions/t-method.md))。

## 与类似指标比较

* **页面事件与[页面视图](page-views.md)**: 页面事件会计算链接跟踪调用()`tl()`的数量，并不包括页面视图跟踪调用(`t()`)。 页面视图则相反； 它会计算页面视图跟踪调用的数量，并不包括链接。
