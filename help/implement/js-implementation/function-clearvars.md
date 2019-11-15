---
description: 从实例对象中清除以下值。此函数会删除以下元素（将其设为“未定义”）。
keywords: Analytics Implementation
solution: Analytics
title: s.clearVars() 函数
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.clearVars() 函数

从实例对象中清除以下值。此函数会删除以下元素（将其设为“未定义”）。

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

例如：

```js
s.clearVars()
```

>[!NOTE]
>
>`clearVars()` 已加入到 [AppMeasurement for JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) 中，但在 H 代码及更早版本中无法使用。

