---
title: 页面查看
description: 页面的查看次数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 2%

---


# 页面查看

“页面视图”度量显示给定维度项目在页面上设置或保留的次数。 它是报告中最常见和最基本的指标之一。

## 如何计算此度量

此度量计算报表包中的所有页面视图[`t()`](/help/implement/vars/functions/t-method.md)跟踪调用()。 对于维，它包括定义或保留维项的点击。 它不包括链接跟踪调用([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 与类似指标比较

* **页面视图与访[问](visits.md)**: 页面视图计算页面的查看次数。 访问量计算访客的会话数。 一次访问包含一个或多个页面。
* **页面视图与[页面事件](page-events.md)**: 页面视图计算页面视图跟踪调用(`t()`)的数量，并不包括链接跟踪调用(`tl()`)。 页面事件则相反； 它会计算链接跟踪调用的数量，并不包括页面视图。