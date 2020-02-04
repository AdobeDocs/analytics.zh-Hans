---
title: purchaseID
description: 根据唯一购买标识符消除重复点击。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# purchaseID

该变 `purchaseID` 量有助于防止包含相同购买的点击量膨胀报告。 例如，如果访客到达您的购买确认页面，您通常会将交易所产生收入的相关数据发送至Adobe。 如果用户多次刷新此页面或将页面书签化以稍后访问，则这些点击会夸大报告。 当多 `purchaseID` 次点击具有相同的购买ID时，变量可消除重复的度量。

当Adobe将点击识别为重复购买时，所有转化数据（如eVar和事件）都不会显示在报告中。 在数据源中， `duplicate_purchase` 列设置为 `1`。

购买ID适用于所有访客，且不会过期。 如果一个访客设置了给定的购买ID，那么另一个访客在一年后设置了相同的购买ID，则第二个购买将消除重复。

## Adobe Experience Platform Launch中的购买ID

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.purchaseID和启动自定义代码编辑器

变 `s.purchaseID` 量是包含购买的唯一标识符的字符串。 它设置为与购买事件相同的点击。 仅使用字母数字字符填充此变量。

此变量最多可存储20字节；长于20字节的值会被截断。 如果此截断值与后续截断值匹配，则会消除这些后续点击的重复性。

```js
s.purchaseID = "ABC123";
```

> [!NOTE] 请勿使用随机化函数生成购买ID。 Adobe recommends using a [data layer](../../prepare/data-layer.md) to store a given purchase ID.
