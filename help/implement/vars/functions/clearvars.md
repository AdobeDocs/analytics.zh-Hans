---
title: clearVars
description: 从实例对象中清除以下值。此函数会删除以下元素（将其设为“未定义”）。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# clearVars

某些实现（如在单页应用程序上）需要在同一页面加载时发送多个点击。 使用该 `clearVars()` 方法清除变量值，以便它们不会保留到后续点击中。

此方法不采用任何参数，也不返回任何值。 它的唯一目的是从实例对象中清除变量值。 此方法将以下元素设置为 `undefined`:

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

## 在Adobe Experience Platform Launch中清除变量

设置配置规则时的清除变量操作。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Rules] 然后单击所需的规则（或创建规则）。
4. 在 [!UICONTROL Actions]下，单击“+”图标
5. 将下拉 [!UICONTROL Extension] 列表设置为Adobe Analytics，将其设置为 [!UICONTROL Action Type] to [!UICONTROL Clear Variables]。

## AppMeasurement中的s.clearVars()和启动自定义代码编辑器

在实例化Analytics对 `s.clearVars()` 象实例后，您可以在实施中的任意位置调用该方法。

```js
s.clearVars();
```
