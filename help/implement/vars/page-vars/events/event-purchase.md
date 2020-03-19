---
title: 购买事件
description: 使用购买事件收集“订单”、“件数”和“收入”指标的数据。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 购买事件

购买事件是变量中的一个 `events` 值。 此值对于希望收集其站点所生成收入相关数据的组织很有用。 它严重依赖于变量 [`products`](../products.md) 和变 [`purchaseID`](../purchaseid.md) 量。

在设置购买事件时，它会影响以下指标：

* “订单”量度以1为单位递增
* “单位”量度以变量中的产品数为增 `products` 加
* “收入”指标通过变量中的价格参数之和增 `products` 加

## 在Adobe Experience Platform Launch中设置购买活动

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Rules] 然后单击所需的规则（或创建规则）。
4. 在下 [!UICONTROL Actions]面，单击现有 [!UICONTROL Adobe Analytics - Set Variables] 操作或单击“+”图标。
5. 将下拉 [!UICONTROL Extension] 列表设置为Adobe Analytics，将其设置为 [!UICONTROL Action Type] to [!UICONTROL Set Variables]。
6. 找到该 [!UICONTROL Events] 部分，然后将事件下拉列表设置为 [!UICONTROL purchase]。

其他从属变量(如 `products` 和) `purchaseID` 在启动项中没有专用字段。 对这些变量使用AppMeasurement语法后面的自定义代码编辑器。

## 在AppMeasurement和Launch自定义代码编辑器中设置购买事件

purchase事件是设置为events变量一部分的字符串。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 购买活动重复数据消除

当您触发购买事件时，Adobe会检查以下各项：

* 点击是否包含变 `purchaseID` 量？ 否则，Adobe将使用点击中的信息创建“临时购买ID”。 此临时购买 ID 仅适用于点击对应的访客。之前的5个临时购买ID存储为每个报表包的每个访客ID。
* 临时购买ID是否与最后五个存储的临时购买ID中的任意一个匹配？ 如果存在匹配，那么图像请求将被视为重复购买。包括购买事件在内的所有转化变量都不会显示在报表中。
* 如果定 `purchaseID` 义了变量，它是否与所有访客在报表包中收集的任何值匹配？ 如果存在匹配，那么图像请求将被视为重复购买。包括购买事件在内的所有转化变量都不会显示在报表中。
