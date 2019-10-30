---
description: 从实例对象中清除以下值。此函数会删除以下元素（将其设为“未定义”）。
keywords: Analytics 实施
seo-description: 从实例对象中清除以下值。此函数会删除以下元素（将其设为“未定义”）。
seo-title: s.clearVars() 函数
solution: Analytics
title: s.clearVars() 函数
topic: 开发人员和实施
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

> [!NOTE]`clearVars()` 已加入到 [AppMeasurement for JavaScript](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) 中，但在 H 代码及更早版本中无法使用。

