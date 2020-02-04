---
title: maxDelay
description: 确定AppMeasurement在发送图像请求之前等待DFA响应的最长时间。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

The `s.maxDelay` variable is used in the DFA data connector to determine the timeout period in contacting the DFA host. 如果Adobe在此变量中设置的指定时间段内未收到来自DFA服务器的响应，则会切断连接，并正常处理数据。 如果您对DFA在每个页面上的响应时间感到担忧，请在您的实施中包含此变量。 Adobe建议尝试使用此值来确定最佳超时时间。

此变量仅在使用DFA数据连接器的实现中使用。 即使使用DFA的实现，此变量也是可选的。

## Adobe Experience Platform启动的最大延迟

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和Launch自定义代码编辑器中的s.maxDelay

该 `s.maxDelay` 变量是一个整数，表示AppMeasurement等待DFA响应的毫秒数。 如果AppMeasurement未及时收到来自DFA的响应，则将向Adobe发送图像请求，而不包含DFA数据。

```js
s.maxDelay = 750;
```

## 属性

* 增加等待时间会收集到更多的 DFA 数据，但这也会增加 Analytics 点击数据丢失的风险。Losing Analytics hit data happens when the user navigates away from the page during the `s.maxDelay` period.
* 缩短等待时间可降低丢失Analytics点击数据的风险，但可以减少随点击数据发送的DFA数据量。
* Losing DFA integration data happens when the `s.maxDelay` period does not accommodate enough time for the DFA host to respond.

> [!NOTE]Adobe 不会控制 DFA 的响应时间。如果即使在将最大延迟时间提高到合理的时间范围后，您也会看到一致的问题，请咨询贵组织的DFA帐户管理员。
