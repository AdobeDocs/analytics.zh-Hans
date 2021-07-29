---
title: clearVars
description: 从实例对象中清除以下值。此函数会删除以下元素（将其设为“未定义”）。
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 87%

---

# clearVars

某些实施（如在单页应用程序上）在同一页面加载过程中需要发送多个点击。使用 `clearVars()` 方法可清除变量值，以便它们不会保留在后续点击中。

此方法不接受任何参数，也不返回任何值。它的唯一用途是从实例对象中清除变量值。此方法可将以下元素设置为 `undefined`：

* `prop1` - `prop75`
* `eVar` -  `eVar250`
* `hier1` -  `hier5`
* `list1` -  `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## 在Adobe Experience Platform中使用标记清除变量

配置规则时设置“清除变量”操作。

1. 使用您的Adobe ID凭据登录到[数据收集UI](https://experience.adobe.com/data-collection)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击“+”图标
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 清除变量]。

## AppMeasurement 和 自定义代码编辑器中的 s.clearVars()

在实例化 Analytics 对象实例后，您可以在实施中的任意位置调用 `s.clearVars()` 方法。

```js
s.clearVars();
```
