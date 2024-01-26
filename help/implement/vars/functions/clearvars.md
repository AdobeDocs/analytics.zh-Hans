---
title: clearVars
description: 清除实例对象中的值。
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 67%

---

# clearVars

某些实施（如在单页应用程序上）在同一页面加载过程中需要发送多个点击。使用 `clearVars()` 方法可清除变量值，以便它们不会保留在后续点击中。

此方法不接受任何参数，也不返回任何值。它的唯一用途是从实例对象中清除变量值。此方法可将以下元素设置为 `undefined`：

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## 使用Web SDK清除变量

当您使用Web SDK将数据发送到Adobe时，所有XDM数据都会自动清除。

## 使用Adobe Analytics扩展清除变量

配置规则时设置“清除变量”操作。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击“+”图标
5. 设置 [!UICONTROL 扩展名] Adobe Analytics的下拉列表，以及 [!UICONTROL 操作类型] 到 [!UICONTROL 清除变量].

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.clearVars()

在实例化 Analytics 对象实例后，您可以在实施中的任意位置调用 `s.clearVars()` 方法。

```js
s.clearVars();
```
