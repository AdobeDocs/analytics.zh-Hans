---
title: purchaseID
description: 根据唯一购买标识符删除重复点击。
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '254'
ht-degree: 100%

---

# purchaseID

`purchaseID` 变量有助于防止包含相同购买的点击使报表虚增。例如，如果访客进入您的购买确认页面，您通常会将交易产生收入的相关数据发送至 Adobe。如果用户多次刷新此页面或将页面添加到书签以供稍后访问，则这些点击会使报表虚增。当多次点击具有相同的购买 ID 时，`purchaseID` 变量会删除重复量度。

当 Adobe 将点击识别为重复购买时，所有转化数据（如 eVar 和事件）都不会显示在报表中。在数据馈送中，`duplicate_purchase` 列被设置为 `1`。

购买 ID 适用于所有访客，且不会过期。如果一个访客设置了给定的购买 ID，然后另一个访客在一年后设置了相同的购买 ID，则将会对第二次购买进行重复数据删除。

## Adobe Experience Platform Launch 中的购买 ID

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.purchaseID

`s.purchaseID` 变量是一个字符串，其中包含购买的唯一标识符。它在相同的点击中被设置为购买事件。仅使用字母数字字符填充此变量。

此变量最多可存储 20 字节；长于 20 字节的值会被截断。如果此截断值与后续截断值匹配，则会删除这些后续点击中的重复项。

```js
s.purchaseID = "ABC123";
```

如果使用`digitalData` [数据层](../../prepare/data-layer.md)：

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>请勿使用随机化函数生成购买 ID。
