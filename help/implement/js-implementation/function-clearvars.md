---
description: 从实例对象中清除以下值。此函数会删除以下元素（将其设为“未定义”）。
keywords: Analytics 实施
seo-description: 从实例对象中清除以下值。此函数会删除以下元素（将其设为“未定义”）。
seo-title: s.clearVars() 函数
solution: Analytics
title: s.clearVars() 函数
topic: 开发人员和实施
uuid: 43c425bc-15ae-4892-a5 a5-e defcb25 ff4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
>`clearVars()` 包含在 [AppMeasurement for JavaScript](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) 中，但在H代码和先前版本中不可用。

