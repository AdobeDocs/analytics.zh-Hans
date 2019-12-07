---
description: 了解purchaseID变量，它有助于防止在Adobe Analytics中显示重复购买。
keywords: duplicate,purchase,purchaseid,s.purchaseid
subtopic: Variables
title: purchaseID
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# purchaseID

The `purchaseID` variable is used to keep an order from being counted multiple times in reporting. Whenever the purchase event is used on your site, Adobe recommends using the `purchaseID` variable.

当访客从您的网站购买商品时， `purchaseID` 通常会在“感谢”或“订单确认”页面填充商品。 在触发 `purchaseID` 购买事件的同时设置变量。 当定 `purchaseID` 义为唯一值时，转化变量值仅计入具有该唯一购买ID的点击。 定义该页面 `purchaseID` 很有价值，因为访客通常会为购买确认页面添加书签以用于自己的目的。 如果您的实施不使用， `purchaseID`则访客刷新页面可轻松夸大转化数据（如收入）。

除购买数据外，对于具有相同购买ID的点击，所有转化变量和事件不会被多次计数。

## 语法

该 `purchaseID` 变量可以包含任何字母数字值，最多20字节。 如果您设置的购买ID长于20字节，则此值将被截断。

```js
s.purchaseID = "uniqueid";
```
