---
title: purchaseID
description: 根据唯一购买标识符删除重复点击。
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 4bd46fd5a9b98bcca67a66c87c9bca67fa00061a
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 73%

---

# purchaseID

`purchaseID` 变量有助于防止包含相同购买的点击使报表虚增。例如，如果访客进入您的购买确认页面，您通常会将交易产生收入的相关数据发送至 Adobe。如果用户多次刷新此页面或将页面添加到书签以供稍后访问，则这些点击会使报表虚增。当多次点击具有相同的购买 ID 时，`purchaseID` 变量会删除重复量度。

当 Adobe 将点击识别为重复购买时，所有转化数据（如 eVar 和事件）都不会显示在报表中。在数据馈送中，`duplicate_purchase` 列被设置为 `1`。

购买ID适用于所有访客，并在37个月后过期。 如果一个访客设置了给定的购买 ID，然后另一个访客在一年后设置了相同的购买 ID，则将会对第二次购买进行重复数据删除。

## 使用Web SDK的购买ID

购买ID会映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.commerce.order.purchaseID`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.purchaseID`

## 使用Adobe Analytics扩展购买ID

您可以在配置Analytics扩展时（全局变量）或根据规则设置购买ID。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 购买ID]部分。

您可以将购买ID设置为值或数据元素。 您还可以从其他 Analytics 变量复制值。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.purchaseID

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
